---
title: CentOS7 MariaDB install
author: cotes
date: 2023-01-06 20:55:00 +0800
categories: [Blogging, Tutorial]
tags: [getting started]
pin: true
---

# Centos7 mariadb 설치

```
yum update -y
```

```
vi /etc/yum.repos.d/MariaDB.repo

(아래내용 추가)
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos7-amd64/
gpgkey = https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck = 1
```

```
yum install mariadb mariadb-server	마리아DB설치

rpm -qa | grep -i mariadb	설치확인

systemctl start mariadb	실행

mysqladmin -u root password qwer1234	마리아DB 패스워드 설정

systemctl enable mariadb	부팅시 자동실행
```

```
MariaDB 접속명령어

mysql -u root -p		
qwer1234
```


## mariadb 데이터경로 /data 로 변경

```
systemctl stop mariadb

yum install -y rsync

rsync -av /var/lib/mysql /data	이동할 경로

vim /etc/my.cnf.d/server.cnf 

아래내용 추가
[mysqld]
datadir=/data
skip-grant-tables
```

```
vi /usr/lib/systemd/system/mariadb.service 

65 : # Prevent accessing /home, /root and /run/user 
     #ProtectHome=true	주석하는 줄
     ProtectHome=false	신규 추가 줄
```

```
service mariadb restart	마리아DB 재시작
```

```
Warning: mariadb.service changed on disk. Run 'systemctl daemon-reload' to reload units.
Job for mariadb.service failed because the control process exited with error code. See 
"systemctl status mariadb.service" and "journalctl -xe" for details. ----에러시
```

```
systemctl daemon-reload

chown -R mysql: /datas
```