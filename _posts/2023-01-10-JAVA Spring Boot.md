---
title: JAVA Spring Boot 설치
author: J
date: 2023-01-10 13:15:00 +0800
categories: [JAVA]
tags: [java spring boot]
pin: true
---

# JAVA Spring Boot

## VS code 환경에서 진행

## 1. 설치하기

![img](/assets/img/favicons/js01.png)
![img](/assets/img/favicons/js02.png)
- Extension Pack for Java 검색 후 ' install '

![img](/assets/img/favicons/js03.png)
- Spring Boot Extension Pack 검색 후 ' install '

## 2. Spring Boot Project Create

단축키 [Ctrl] + [Shift] + [P] 입력해서 Spring initializr을 입력 후 아래 내용 참고

![img](/assets/img/favicons/js04.png)
![img](/assets/img/favicons/js05.png)

```
com.example (Group id) -> 엔터
demo (Artifact ID)     -> 엔터
```

![img](/assets/img/favicons/js06.png)
![img](/assets/img/favicons/js07.png)
![img](/assets/img/favicons/js08.png)
```
Spring Web 체크 시 추가 라이브러리를 설치한다.

마지막으로 엔터 입력 후 스프링 부트를 설치할 폴더를 지정하면 설치가 완료 된다.
```

## Spring Boot 실행 하기

```
src / main / resources 경로 밑에 static 이라는 폴더가 없으면 생성 후 
static 폴더 아래에 index.html 파일을 생성한다.
```
- index.html 파일 안에서 [ ! ] (느낌표) 를 누르면 HTML5 기본양식이 자동완성된다. 

![img](/assets/img/favicons/js09.png)
- 위와 같이 양식 작성후 [Ctrl] + [s] 저장

![img](/assets/img/favicons/js10.png)
```
src / main / java / com / test / test 경로 아래에 있는 TestApplicationjava 클릭 후 우측상단 [Run java] 로 실행
```
- [F5] 단축키로도 실행 할 수 있다.

![img](/assets/img/favicons/js11.png)
![img](/assets/img/favicons/js12.png)

## 확인

- ( http://localhost:8080/ ) 주소로 웹사이트로 접속해보면 기존에 작성했던 index.html 파일이 웹브라우저로 열리는걸 확인할 수 있다.