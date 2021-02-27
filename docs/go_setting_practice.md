# Golang Setting 해보기(Unix system 기준)
## 1. GOPATH 설정하기
어떤 위치에 나의 workspace를 만들지 설정하는 작업.
1. 설정파일로 이동
```sh
$ vim ~/.bash_profile
```
혹은
```sh
$ vim ~/.zshrc
```
> `.bash_profile`이 없는 경우가 있다. 당황하지 말고 직접 만들어주면 된다:) Don't panic. Just Make it!
2. GOPATH 설정하는 명령어 추가
GOPATH=`원하는 경로`
```sh
export GOPATH=$HOME/myworkspace
```
## 2. 실제 경로 만들기
설정한 경로에 해당하는 실제 파일구조를 만든다.
```sh
$ cd ~
$ mkdir myworkspace
```
앞으로 위 폴더 안에 프로젝트에 필요한 것들이 모두 담기게 된다.
## 3. 프로젝트 경로 만들기
우리가 실제로 치는 코드는 `GOPATH`하위의 `src`폴더에 담기게 된다.<br>
git으로 코드를 관리한다는 전제하에 아래와 같은 경로로 코드를 관리하기로 약속한다.
```
myworkspace/src/github.com/:username/:projectname
```
- `:username`: 본인의 깃허브 아이디
- `:projectname`: 프로젝트명, 레포지터리 이름과 통일한다.
```sh
$ cd myworkspace
$ mkdir src
$ cd src
$ mkdir github.com
$ cd github.com
$ mkdir :username
$ cd :username
$ mkdir hello
```
예제 프로젝트 이름은 `hello`!
## 4. vscode에서 프로젝트 코드 치기
1. vscode를 열고 `open folder`클릭
2. 위에서 설정한 프로젝트 폴더 열기(myworkspace/src/github.com/:username/hello)
3. helloworld.go 파일 만들기
```go
package main

import "fmt"

func main() {
	fmt.Println("hello, world")
}
```
## 5. GO 명령어 쳐보기
### go vet
아무 문제 없다면 아무것도 뜨지 않아요.
일부러 오타를 낸 후 go vet을 쳐보면 몇 번째 줄에서 무엇이 잘못됐는지 알려줍니다.
#### 오타를 낸 경우
아래는 일부러 `fmt`를 `famt`로 잘못 표기했습니다.
```go
famt.Println("hello, world")
```
이후 `go vet`을 입력하면 아래와 같이 에러를 알려줍니다.
```sh
# github.com/:username/hello
vet: ./helloworld.go:4:2: undeclared name: famt
```
### go run

아래와 같이 입력하면
```sh
go run ./helloworld.go
```
아래와 같은 결과가 나옵니다.
```
hello, world
```
### go install
```sh
go install
```
위와 같이 입력하면 `$GOPATH`아래에 `bin`폴더가 생기고 그 안에 프로젝트 실행파일이 담깁니다.
bin폴더로 이동해 확인해봅시다.
```sh
$ cd /myworkspace/bin
$ ls
```
`hello`라는 실행파일이 생긴 것을 볼 수 있다. 실행해보자.
```sh
$ ./hello
```
아래와 같은 결과가 나옵니다.
```
hello, world
```




### + 어떤 위치에서든 프로젝트파일을 실행시키고 싶다면
`.bash_profile` 혹은 `.zshrc`에 가서 다음과 같은 명령어를 추가한다.
```sh
export PATH=$PATH:$GOBIN
```
> `$GOBIN`의 default값은 `$GOPATH/bin`이다.
