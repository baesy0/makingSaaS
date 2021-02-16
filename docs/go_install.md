# Download & Install
- [홈페이지에서 다운로드](https://golang.org/doc/install)
- 명령어로 다운로드
### macOS인 경우
```sh
brew install go
```
### linux
### windows
필요할 때 업데이트하겠다.
# Setting
## workspace setting
### workspace란?
- go code가 저장되는 장소.
- 환경변수 `GOPATH`로 지정할 수 있다.
- 현재는 GOPATH이외의 장소에 project를 저장해도 괜찮다고 한다.
### setting GOPATH
- 지정하지 않으면, 기본적으로
  - Unix systems에서는 `$HOME/go`
  - Windows에서는 `%USERPROFILE%\go`으로 지정된다.
- Unix system
  - bash쉘이라면 아래 명령어를 `~/.bash_profile`파일에 입력한다.
  - zsh 쉘이라면 아래 명령어를 `~/.zshrc` 파일에 입력한다.
```sh
export GOPATH=$HOME/go
```
- Windows
  - 필요하면 아래 레퍼런스 링크 참고 

## reference
- https://sleepydeveloper.tistory.com/entry/Golang-4-Workspace-개념-및-폴더-생성
- https://www.callicoder.com/golang-installation-setup-gopath-workspace/
- https://github.com/golang/go/wiki/SettingGOPATH
