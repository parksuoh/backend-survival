# 1-3 HTTP Server

* Listen

80번 포트가 사용중이라면 다른포트를 사용한다.

int port = 8080;

ava에서는 ServerSocket이라는 별도의 클래스를 사용 (Socket을 상속한게 아니라 완번히 구별된다는점 주의).

ServerSocket listener = new ServerSocket(port);

클라이언트의 접속을 기다림.

클라이언트가 접속하면 소켓을 따로 만들어서 돌려줌

Socket socket = listener.accept();

I/O에서 기다리는걸 Blocking이라고 함

근데 여기서 지연되거나 영원히 기다리는 일이 벌어질 수 있음

멀티쓰레드나 비동기, 이벤트 기반 처리로 해결가능하다.



* Request

클라이언트와 동일



* Response

클라이언트의 요청처럼 응답 메시지를 만들어서 전송하면 됨

HTTP/1.1 200 OK&#x20;

(빈 줄)&#x20;

Hello, world!



Java 코드

```
String message = """ HTTP/1.1 200 OK
Hello, world!
""";
```

또는

String message = "" +&#x20;

"HTTP/1.1 200 OK\n" +&#x20;

"\n" +&#x20;

"Hello, world!\n";

개행 신경쓰자



전체적으로 구성은 이러하다

String body = "Hello, world!";&#x20;

byte\[] bytes = body.getBytes();&#x20;

String message = "" +&#x20;

"HTTP/1.1 200 OK\n" +&#x20;

"Content-Type: text/html; charset=UTF-8\n" + "Content-Length: " + bytes.length + "\n" +&#x20;

"\n" +&#x20;

body;

Content-Length로 정확한 크기를 알 수 있기 때문에 마지막 줄에 Newline(\n)을 넣지 않아도 됨



* close

클라이언트와 동일

