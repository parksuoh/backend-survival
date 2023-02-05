# 1-5 Spring Web MVC

1. View 는 눈으로 보여지는 영역을 말한다.
2. Controller 는 데이터를 적절히 가공하는 역할을한다.
3. Model은 그외 모든것을 말한다.



* 관심사 분리

MVC가 추구하는건 UI 와 비지니스 로직을 분리하는것이다.

* View에서 참조하는 표현/데이터



* Controller

@RestController&#x20;

public class WelcomeController {&#x20;

&#x20;      @GetMapping("/")&#x20;

&#x20;       public String home() {&#x20;

&#x20;           return "Hello, world!";&#x20;

&#x20;       }&#x20;

}
