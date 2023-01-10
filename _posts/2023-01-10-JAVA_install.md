---
title: JAVA 설치
author: J
date: 2023-01-10 13:15:00 +0800
categories: [JAVA]
tags: [java]
pin: true
---

# JAVA 설치하기

## Windows / VSCode 환경에서 진행

## 1. JDK 파일 다운로드

먼저 자바를 설치하려면 JDK파일을 다운 받아야한다.

링크 : https://www.oracle.com/java/technologies/downloads/

zip파일로 다운받아서 C: 밑에 압축 해제한다.

![img](/assets/img/favicons/java01.png)
![img](/assets/img/favicons/java02.png)

## 2. PATH / 환경변수 설정

환경변수 설정을 통해 윈도우 환경에서 자바를 인식할 수 있도록 설정한다.

![img](/assets/img/favicons/java03.png)
![img](/assets/img/favicons/java04.png)
![img](/assets/img/favicons/java05.png)
![img](/assets/img/favicons/java06.png)
```
시스템 변수 추가

JAVA_HOME
C:\jdk-19.0.1
```
![img](/assets/img/favicons/java07.png)
```
시스템 변수 추가

CLASSPATH
%JAVA_HOME%\lib
```
![img](/assets/img/favicons/java08.png)
![img](/assets/img/favicons/java09.png)
```
Path 내용 편집

%JAVA_HOME%\bin
```

## 3. 확인

CMD 명령 프롬프트 창에 입력

```
java -version
```
아래와 같은 화면이 나오면 설치 및 환경변수가 제대로 적용된 것이다.

![img](/assets/img/favicons/java10.png)