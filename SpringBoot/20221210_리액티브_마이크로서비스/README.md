# 20221210_리액티브_마이크로서비스

### Spring WebFlux

Netty라는 어플리케이션 서버를 이용하여 리액티브 마이크로 서비스를 만들 수 있는 스프링 프레임워크 5.0 컴포넌트

### 구독자와 게시자, 이벤트

##### 이벤트

```
버튼 누르기, 스크롤 등 사용자 작업
```

##### 구독자

```
이벤트를 수신할 때 사용하는 객체
이벤트가 생성될 때 이벤트를 수신해야하는 책임이 있음
```

##### 게시자

```
이벤트를 발생시키는 책임이 있는 객체
```

&nbsp;
&nbsp;


### Mono

리액티브 게시자를 정의하는 방법을 제공하는 클래스
단, 하나의 결과만 보낼 수 있음

```kotlin
val customerMono: Mono<Customer> = Mono.just(Customer(1, "Mono"))
```

리액터는 코틀린을 위한 고차함수를 제공 함
```kotlin
val customerMono = Customer(1, "Mono".toMono())
```

### Flux

0에서 무한대의 요소를 가진 게시자를 생성하는 클래스

```kotlin
val customerFlux = Flux.fromIterable(listOf(Customer(1, "One"), Customer(2, "Two)))
```

고차함수로 표현

```kotlin
val customerFlux = listOf(Customer(1, "One"), Customer(2, "Two)).toFlux()
```

### RouterFunction 사용

```kotlin
@Component
class CustomerRouter {

    @Bean
    fun customerRoutes(): RouterFunction<*> = router {
        "/functional".nest {
            "/customer".nest {
                GET("/") {
                    ok().body("hello world".toMono(), String::class.java)
                }
            }
        }
    }
}
```

