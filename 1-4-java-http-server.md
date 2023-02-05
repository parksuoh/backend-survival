---
description: Java HTTP Server 는 내부적으로 Non-blocking_I/O를 사용하는 고수준 HTTP 서버 API
---

# 1-4 Java HTTP Server



1. 서버 객체 준비

InetSocketAddress address = new InetSocketAddress(8080); int backlog = 0;

HttpServer httpServer = HttpServer.create(address, backlog);

2. URL (정확히는 path)에 핸들러 지정

httpServer.createContext("/", (exchange) -> {&#x20;

&#x20;  // TODO&#x20;

});

3. Listen

httpServer.start();



* Request

1. HTTP Method

String method = exchange.getRequestMethod();&#x20;

System.out.println(method);

2. HTTP path

URI uri = exchange.getRequestURI();&#x20;

String path = uri.getPath();&#x20;

System.out.println(path);

2. Headers

Headers headers = exchange.getRequestHeaders();&#x20;

for (String key : headers.keySet()) {    &#x20;

&#x20; System.out.println(key + ": " + headers.get(key));&#x20;

}

2. Body

InputStream inputStream = exchange.getRequestBody();&#x20;

String body = new String(inputStream.readAllBytes());&#x20;

System.out.println(body);

* Response

1. 데이터를 Byte 배열로 준비.

String body = "Hello, world!";&#x20;

byte\[] bytes = body.getBytes();

1. HTTP Status Code와 Content-Length 지정.

exchange.sendResponseHeaders(200, bytes.length);

1. 데이터 전송.

OutputStream outputStream = exchange.getResponseBody(); outputStream.write(bytes); outputStream.flush();



\
