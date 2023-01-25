---
title: yarn_error
author: J
date: 2023-01-25 13:15:00 +0800
categories: [React, Yarn]
tags: [react, java, yarn]
pin: true
---

# yarn 명령어 에러 해결

### 프로젝트로 React를 사용중에 yarn 명령어 이슈발생

```
yarn 명령어는 npm 명령어와 비슷한 느낌이다. 무언가를 실행시킬때 사용하는 명령어

 ex) yarn start, npm start, yarn install, npm install 

내 개인적인 생각으로는 리눅스의 yum 명령어랑 비슷한 느낌인 것 같다.
```

Node.js를 설치했음에도 불구하고 yarn 명령어를 사용했는데 아래와 같은 보안에러가 발생했다.

![img](/assets/img/favicons/yarn_error.png)

확인해보니 스크립트의 실행 권한으로 발생하는 문제라고 한다.

문제 해결방법은 생각보다 간단했다.

1. 윈도우 PowerShell 프로그램을 관리자권한으로 실행
2. Get-ExecutionPollcy 라는 명령어를 입력하면 Restricted 로 기본 설정값으로 있을 것이다.
![img](/assets/img/favicons/yarn_error2.PNG)
3. Set-ExecutionPolicy RemoteSigned > Y
![img](/assets/img/favicons/yarn_error3.PNG)
4. 확인 > yarn -v 또는 yarn 입력시
버전이 제대로 표시된다면 이슈가 해결된것
