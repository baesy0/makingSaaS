# webserver 구축하기
## 예제코드

```go
package main
 
import (
    "net/http"
)
 
func main() {
    http.HandleFunc("/", handleInit)
    http.HandleFunc("/bae", handleBae)
 
    http.ListenAndServe(":8080", nil)
}

func handleInit(w http.ResponseWriter, r *http.Request) {
	fmt.Fprint(w, "hello world")
}
func handleBae(w http.ResponseWriter, r *http.Request) {
	fmt.Fprint(w, "hello bae")
}
```
### 서버 구동하기
```http.ListenAndServe(A, B)```

ListenAndServe는 지정한 포트를 Listen하고 있다가 신호가 오면 Serve하는 함수다.<br>
A에서는 포트넘버를, B에서는 어떤 ServeMux를 사용할지 지정한다.

### 핸들러 추가하기
`Handle()`, `HandleFunc()`를 쓸 수 있다.<br>
두 메서드는 요청된 Request Path에 어떤 Request 핸들러를 사용할 지 지정하는 라우팅 역할을 한다.
<br>
`handleFunc(A, B)`

A에서는 URL을 받는다.<br>
B에는 해당 URL일 경우 실행할 코드(함수)가 들어간다.<br>
예제에서는 함수를 만들고 해당 함수 이름을 넣었다.<br>


## 다음 단계
다음 문서에서는 커맨드라인 명령어로 서버를 구동할 수 있도록 할 예정.
