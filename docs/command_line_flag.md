# Command Line Flag 만들기
## 목적
- 테스트하기도 편하고
- 커맨드라인으로도 실행할 수 있고
- 편리하당
## 방법
Go는 커맨드라인 플래그 파싱을 지원하는 flag 패키지를 제공합니다.
이 패키지를 사용하여 커맨드라인 플래그를 만들어 볼거에요.
### step 1. 플래그를 담을 변수를 만든다.
```go
flagVar := flag.Bool("nameofflag", default value, "description of flag")
```
- 변수의 데이터 타입을 설정한다.
  - `flag.Bool`, `flag.String`, `flag.Int`
  - 위 함수들은 포인터를 반환한다.
  - ex) `flag.String`의 반환값: 문자열 포인터
- `플래그 이름`, `디폴트값`, `해당 플래그에 대한 설명`을 인수로 넘겨준다.

```go
package main

import "flag"

func main() {
  flagTest := flag.Bool("test", false, "flag for test")
  flagName := flag.Bool("name", false, "name of project")
}
```
### step 2. 플래그를 파싱해줄 함수를 호출한다
```go
flag.Parse()
```
```go
package main

import "flag"

func main() {
  flagTest := flag.Bool("test", false, "flag for test")
  flagName := flag.Bool("name", false, "name of project")

  flag.Parse()
}
```
### step 3. if문으로 각 플래그별 실행될 코드를 나누어준다.
```go
package main

import (
	"flag"
	"fmt"
	"os"
)

func main() {
  flagTest := flag.Bool("test", false, "flag for test")
  flagName := flag.Bool("name", false, "name of project")
  
  flag.Parse()

	if *flagTest {
		fmt.Println("This is flag test")
		os.Exit(0)
	} else if *flagName {
		fmt.Println("the name of this project is hello")
		os.Exit(0)
	} 
}
```
> 여기서는 각 플래그 별 코드가 실행된 후 프로그램이 종료되도록 했습니다(`os.Exit(0)`)
### step 4. 해당하는 플래그가 없을 경우 출력한 도움말 추가하기
```go
flag.Usage()
```
>`명령어 -h` 혹은 `명령어 --help`로도 출력할 수 있어요.

```go
package main

import (
	"flag"
	"fmt"
	"os"
)

func main() {
  flagTest := flag.Bool("test", false, "flag for test")
  flagName := flag.Bool("name", false, "name of project")
  
  flag.Parse()
  
  if *flagTest {
    fmt.Println("This is flag test")
    os.Exit(0)
  } else if *flagName {
    fmt.Println("the name of this project is hello")
    os.Exit(0)
  } else {
    flag.Usage()
    os.Exit(1)
  }
}
```
### step 5. 실행해보기
```sh
go install
```
---
- 입력
```sh
hello
```
- 출력
```sh
Usage of hello:
  -name
        name of project
  -test
        flag for test
```
---
- 입력
```sh
hello -test
```
- 출력
```sh
This is flag test
```
---
- 입력
```sh
hello -name
```
- 출력
```sh
the name of this project is hello
```
---
- 입력
```sh
hello --help
```
- 출력
```sh
Usage of hello:
  -name
        name of project
  -test
        flag for test
```
