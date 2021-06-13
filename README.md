# makingSaaS
## 목적
- 웹에 SaaS 설치.
- 그 과정에서 완결된 웹서비스를 하나 제작하는 경험하기.
- git을 통한 협업 익히기
- 성공조건: SaaS에 광고를 넣어서 광고비를 최소 4원 번다.
- 레포지터리: [lotto](https://github.com/janghangdong-minions/lotto)
## 준비물
- 개인 컴퓨터(linux계열 OS 권장. 강력히 권장..)
## 과정
1. 첫 날(2021.2.9)
    1. 깃허브 가입
    1. [organization 만들기](/docs/Github_organization.md)
    1. repository 만들기
    1. [vscode setting하기](/docs/vscode_setting.md)
    1. 어떤 서비스를 만들지 토론 / 자료조사
1. golang(2021.2.16)
    1. [다운로드 / install](/docs/go_install.md)
    2. [GO setting](/docs/go_setting.md)
    3. [GO 명령어](/docs/go_cmd.md)
1. code convention 만들기(Wiki)
1. [golang 실습](/docs/go_setting_practice.md)(2021.2.21)
1. Let's git it(2021.2.28)
    1. clone
    2. remote & local
    3. commit & push/pull
    4. upstream & origin
    5. branch
1. [command line flag(커맨드라인 플래그) 만들기](/docs/command_line_flag.md)(2021.3.7)
1. [git actions 설치하기](/docs/git_actions.md)(2021.3.14)
2. Webserver
    1. [웹서버 구축하기](/docs/webserver_setting.md)
    2. [서비스 IP 받아오기](/docs/webserver_get_serviceIP.md)
    3. [cmd로 웹서버를 실행하기](/docs/webserver_executing_via_cmd.md)
5. template(2021.3.28)
6. template이랑 웹서버 연결하기
---
8. bootstrap 다운받기(2021.4.4)
9. html에서 bootstrap 연결하기
11. bootstrap을 이용해 버튼만들고 기능 연결하기
---
13. handle로 페이지 만들고 버튼과 연결하기
---
15. 자료구조 토론하기/정하기
16. 함수에 숫자 띄우기(자료구조 + template문법)
17. 함수만들기(backend)
---
19. 리팩토링(인수를 flag변수로, 디버깅이 쉽도록 cmd로 함수를 실행할 수 있도록 함)
---
21. 함수의 결과값 페이 지에 띄우기(backend result ---link---> frontend)
22. 이쁘게 띄우기
    1. CSS 조사 및 적용
    2. 숫자가 한자리 일 때는 앞에 0붙이기(template function)
23. js 파일 생성 및 html에 연결하기
24. html파일에 js event 추가하기

-----한달 방학(5/9 ~6/6)-----

25. VFS(Virtual File System) 구축
    - 기본적인 요소들은 다 배웠으니 잘 싸서 안정적으로 만들기!)
    - VFS란?
    - 
