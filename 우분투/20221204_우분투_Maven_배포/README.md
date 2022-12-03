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

### 프로젝트 내 mvnw 파일 권한 설정
```bash
sudo chmod +x mvnw
```

&nbsp;
&nbsp;


### 프로젝트 빌드
```bash
./mvnw clean package
```