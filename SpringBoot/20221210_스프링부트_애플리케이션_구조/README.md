# 20221210_스프링부트_애플리케이션_구조

&nbsp;
&nbsp;

### @SpringbootApplication
```
스프링부트 어플리케이션 부트스트랩
```

### 컴포넌트 스캔
```
스프링부트 애플리케이션이 시작될 때, 애플리케이션 컨텍스트 클래스 아래의 모든 클래스와 패키지를 스캔
```

### @Autowired
```
스프링 컨텍스트에서 빈을 가져와 매핑
```

### yaml
이렇게 생김
```yaml
spring:
    profiles:
        active: "development"
```

### RestController

예시

##### Customer 클래스
```kotlin
data class Customer(var id:Int = 0, var name: String = "", var tel: Telephone)
data class Telephone(var countryCode: String="", var phoneNumber: String)
```

