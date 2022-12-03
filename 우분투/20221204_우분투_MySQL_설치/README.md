# 20221204 우분투 MySQL 설치

&nbsp;
&nbsp;

### 업데이트 & 업그레이드 부터...
```bash
sudo apt-get update
sudo apt-get upgrade
```

&nbsp;
&nbsp;

### MySQL 설치
```bash
sudo apt-get install mysql-server
```

&nbsp;
&nbsp;

### MySQL 실행해보기
```bash
sudo /usr/bin/mysql -u root -p
```

&nbsp;
&nbsp;

### 외부접속을 위한 사용자 만들기
```bash
mysql> CREATE USER 'user'@'%' IDENTIFIED BY 'password';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'user'@'localhost';
mysql> FLUSH PRIVILEGES;
```

&nbsp;
&nbsp;

### ERROR 1410 (42000): You are not allowed to create a user with GRANT 문제 해결

##### 임시로 외부권한 있는 ROOT 유저 생성 후 재 로그인
```bash
mysql> CREATE USER 'root'@'%' IDENTIFIED BY 'root';
```

&nbsp;

##### 원하는 사용자에게 권한을 부여하고, root@'%' 삭제
```bash
mysql> GRANT ALL PRIVILEGES ON *.* TO 'user'@'localhost';
mysql> FLUSH PRIVILEGES;
mysql> DROP USER 'root'@'%';
```

&nbsp;
&nbsp;

### MYSQL 포트 변경

##### 설정파일 열기
```bash
vi /etc/mysql/mysql.conf.d/mysqld.conf
```

##### 포트 & bind-address 수정하기
```bash

...

port        = 0000

...

bind-address           = 0.0.0.0  <<-- 주석처리
mysqlx-bind-address    = 0.0.0.0  <<-- 주석처리
```

##### 저장
```bash
:wq!
```
&nbsp;

##### MySQL 다시 시작
```bash
sudo service mysql restart
```

&nbsp;

##### MySQL 포트확인

MySQL 접속 후 실행
```bash
mysql> SHOW GLOBAL VARIABLES LIKE 'PORT';
```

&nbsp;

##### 포트가 열렸는지 확인
[https://www.yougetsignal.com/tools/open-ports/](https://www.yougetsignal.com/tools/open-ports/)


&nbsp;
&nbsp;

### MySQL 외부접속을 위한 방화벽 해제
```bash
sudo ufw allow PORT/tcp
sudo ufw status
```