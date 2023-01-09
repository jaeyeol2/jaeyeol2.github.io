---
title: Virtualization
author: cotes
date: 2022-12-23 20:55:00 +0800
categories: [Blogging, Tutorial]
tags: [getting started]
pin: true
---


# 가상화 정리 - 2022.12.20

## **가상화란?**

 호스트 OS형은 물리적 하드웨어 위에 OS를 설치해 그 위에 가상화 소프트웨어와 가상머신을 움직이는 방식이다.

 즉, 물리 머신 위에 직접 동작하는 OS를 “Host OS”라고 한다. 또한, 이 Host OS 위에서 동작하는 가상화 머신에 설치된 O/S를 “Guest OS”라 부른다.

**장점** - 가상의 하드웨어를 에뮬레이팅 하기 때문에 호스트 운영체제에 크게 제약사항이 없다

> 에뮬레이팅 : 하나의 시스템이 다른 시스템을 흉내 내도록 하는 것
> 

**단점** - OS위에 OS가 얹히는 방식이기 때문에 오버헤드가 클 수 있다

> 오버헤드 : 어떤 처리를 하기 위해 들어가는 간접적인 처리 시간 · 메모리 등
> 

**종류** -        VMware Workstation        Microsoft Virtual PC             VirtualBox

![img](/assets/img/favicons/host1.PNG)

## **하이퍼바이저 가상화란?**

 하이퍼바이저형은 Host OS없이 하드웨어에 하이퍼바이저를 설치하여 사용하는 가상화 방식이다.

하이퍼바이저라는 소프트웨어를 물리 하드웨어위에 직접 움직여, 하이퍼바이저 위에 가상머신을 움직이게 한다.

하이퍼바이저형의 특징은, 가상머신이 마치 독립한 호스트 시스템과 같이 행동한다는 점이다.

**장점** - 별도의 Host OS가 없기 때문에 오버헤드가 적고, 하드웨어를 직접 제어하기 때문에 효율적으로 리소스를 사용할 수 있다.

**단점** - 자체적으로 머신에 대한 관리 기능이 없기 때문에 관리를 위한 컴퓨터나 콘솔(CLI)이 필요하다.

**종류**

VMware ESX Server (전가상화)       Citrix XenServer (반가상화)                    MS Hyper-v (전가상화)

![https://blog.kakaocdn.net/dn/ww0U5/btrwXzktkgJ/3KtjWwIXuESARwzmxzgwDk/img.png](https://blog.kakaocdn.net/dn/ww0U5/btrwXzktkgJ/3KtjWwIXuESARwzmxzgwDk/img.png)

> **전가상화(Full-Virtualization)** - 전가상화는 하드웨어를 완전히 가상화 하는 방식으로 Hardware Virtual Machine 이라고도 불린다. 모든 가상머신들의 하드웨어 접근이 DOM0을 통해서 이루어진다. 즉, 모든 명령에 대해서 DOM0가 개입을 하게되는 형태다.
> 

![img](/assets/img/favicons//host2.PNG)

> **반가상화(Para-Virtualization)** - 반가상화는 전가상화와 달리 하드웨어를 완전히 가상화 하지 않는다. 하이퍼콜(Hyper Call)이라는 인터페이스를 통해 하이퍼바이저에게 직접 요청을 날릴 수 있다.
> 

![img](/assets/img/favicons//host3.PNG)

## **컨테이너 가상화란?**

 컨테이너형의 컨테이너에는 게스트OS나 가상하드웨어를 포함하지 않고 어플리케이션 동작을 위한 라이브러리와 어플리케이션등으로 구성. 이를 각각 개별 서버처럼 사용 가능하다.

**장점** - 컨테이너 가상화는 오버헤드가 적어 가볍고 빠른 장점이 있다.

**종류**

![https://blog.kakaocdn.net/dn/xCR6D/btrwZ0PFeiJ/2gKegIQWaOUXjrkBnawT91/img.png](https://blog.kakaocdn.net/dn/xCR6D/btrwZ0PFeiJ/2gKegIQWaOUXjrkBnawT91/img.png)

## [정리]

**호스트OS형**은 일반PC에서 VMWare WorkStation을 설치하여 게스트OS를 설치하는 가상화 방식이며 실제 PC의 리소스를 공유하는 방식이다.

**하이퍼바이저형**은 기존 OS위에 윈도우나 리눅스를 설치하는 방식이 아닌 그냥 하드웨어에서 가상화를 위한 OS(VMWare ESXi와 같은 소프트웨어)를 설치후 속에 윈도우, 리눅스 등의 OS를 설치하는 가상화 방식이다.

그렇기 때문에, 하이퍼바이저 가상화의 경우 전용 소프트웨어를 이용하여 기존 OS의 리소스 경유하지않기에 처리 오버헤드가 발생하지 않게 된다.

**컨테이너형**의 경우는 OS가상화가 아닌 소프트웨어를 가상화 하는것에 목적을 둔다. 컨테이너에는 어플리케이션으로만 구성되어있다. ( 컨테이너로 apache, nginx 등을 띄울 수 있다. 개발에 용이 )

OS를 설치하지 않기 때문에 OS를 움직이는데 필요한 리소스를 사용하지 않아 가상화 소프트웨어를 저 지연 고 퍼포먼스 이용이 가능하다.