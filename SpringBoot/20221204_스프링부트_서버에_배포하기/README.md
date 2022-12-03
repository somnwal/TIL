# 20221204_스프링부트_서버에_배포하기

&nbsp;
&nbsp;


### 우분투에서 배포해보기
[20221204_우분투_Maven_배포](https://github.com/somnwal/TIL/tree/main/우분투/20221204_우분투_Maven_배포)

&nbsp;
&nbsp;


### 이클립스에서 Maven Build

1. 프로젝트 혹은 pom.xml 우클릭
2. Run As > Maven Build
3. Goals 항목에 package 입력 후 Run
4. 생성된 .jar 파일 확인

&nbsp;
&nbsp;

### 스프링부트 프로젝트 실행
```bash
java -jar spingboot_project.jar
```

&nbsp;
&nbsp;

### 스프링부트 프로젝트 백그라운드로 실행
```bash
nohup java -jar spingboot_project.jar &
```