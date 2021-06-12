# Git Actions 설치하기
## Git Actions란?
software workflow를 자동화시켜주는 도구.<br>
CI/CD process를 자동화할 수 있다.
- [홈페이지](https://github.com/features/actions)
- [공식문서](https://docs.github.com/en/actions)

##  CI/CD란?
Continuous Integration / Continuous Delivery, Continuous Deployment
<p align = "left">
<img src="/img/CICD_redhat.png" width="550"><br/>
</p>

> image from [redhat](https://www.redhat.com/ko/topics/devops/what-cicd-pipeline)

## 쓰는 이유


## Git Actions 시작하기
1. 레포지터리 상단의 `Actions`탭을 클릭한다.
2. 템플릿 코드(yml파일)를 선택하여 시작한다.
3. 일단 우리는 CI를 위한 코드만 작성한다.(이후 서비스가 완성되고 배포가 가능해진 시점에 다시 수정한다.)

[lotto 프로젝트의 git actions](https://github.com/janghangdong-minions/lotto/blob/main/.github/workflows/go.yml)

### Reference
https://zzsza.github.io/development/2020/06/06/github-action/
https://www.redhat.com/ko/topics/devops/what-cicd-pipeline

