# 20221204_우분투_Maven_배포

&nbsp;
&nbsp;

### 업데이트 & 업그레이드 부터...
```bash
sudo apt-get update
sudo apt-get upgrade
```

&nbsp;
&nbsp;

### 메이븐 설치
```bash
sudo apt install maven
```

&nbsp;
&nbsp;

### 메이븐 설치 확인(버전 확인)
```bash
mvn -v
```

&nbsp;
&nbsp;

### 아파치 & 톰캣 설치
```bash
sudo apt install apache2
sudo apt install tomcat9
```

&nbsp;
&nbsp;

### 톰캣 포트 변경


##### 톰캣 server.xml 파일 수정
```bash
sudo vi /etc/tomcat9/server.xml
```
```bash
...

<Connector port="포트번호" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />

...
```

&nbsp;

##### 톰캣 재시작
```bash
sudo service tomcat9 restart
```

&nbsp;
&nbsp;


### (선택사항) FTP 설치하기
배포할 때, 편의를 위해서 설치 (개인적으로 git이 더 편함..)
```bash
sudo apt install filezilla
```

&nbsp;
&nbsp;

### 호스팅을 위한 유저 생성 및 경로 설정

##### 유저 생성
```bash
adduser costudy
```

&nbsp;

##### 유저 전환
```bash
su -l costudy
```

&nbsp;

##### /home/user/www/ROOT/ 폴더 생성
```bash
mkdir -p www/ROOT
cd www/ROOT
```

&nbsp;

##### 테스트용 index.jsp 생성
```bash
vi index.jsp
```

```java
Hello Tomcat
```

&nbsp;
&nbsp;

### 톰캣 서버 설정
```bash
vi /etc/tomcat9/server.xml
```