# 1-2 HTTP Client

* Connect

클라이언트가 서버랑 연결할때 IP주소 혹은 도메인이름을 사용해야한다. &#x20;

String host = "example.com";

http의 기본 포트번호는 80번이다.

int port = 80;

포트번호와 IP주소를 알면 서버에 접속가능

Socket socket = new Socket(host, port);

만약 여기서 실패하면 실패하면 ConnectException 예외 발생.



* Request

요청 메세지를 만들고 TCP로 전송 할수있음

GET http://example.com/ HTTP/1.1&#x20;

(빈 줄)

또는

GET / HTTP/1.1&#x20;

Host: example.com&#x20;

(빈 줄)

빈줄필수 후자형태를 더 많이씀

Java 코드

<pre><code>String message = """
 GET / HTTP/1.1 
<strong>Host: example.com
</strong><strong>""";
</strong></code></pre>

```

또는
String message = "" +
	"GET / HTTP/1.1\n" +
	"Host: example.com\n" +
	"\n";
```

소켓에서 Output Stream을 얻어서 쓸 수 있음

OutputStream outputStream = socket.getOutputStream();&#x20;

outputStream.write(message.getBytes());



문자열을 직접 전송하고 싶다면 Writer를 씀 (추천하는방법임)

```java
OutputStreamWriter writer = new OutputStreamWriter(socket.getOutputStream());

writer.write(message);
writer.flush();
```

* Response

소켓에서 Input Stream을 얻어서 쓸 수 있음.

InputStream inputStream = socket.getInputStream();

Byte 배열을 준비한다.&#x20;

Byte 배열 < 데이터 이면 반복해서 여러 번 읽는 작업이 필요하다.

byte\[] bytes = new byte\[1\_000\_000]; int size = inputStream.read(bytes);

먼자열로 변환

byte\[] data = Arrays.copyOf(bytes, size); String text = new String(data);

System.out.println(text)



요청과 마찬가지로 Reader를 쓰면 훨씬 편함



InputStreamReader reader = new InputStreamReader(socket.getInputStream());

CharBuffer charBuffer = CharBuffer.allocate(1\_000\_000);

reader.read(charBuffer);

charBuffer.flip();

System.out.println(charBuffer.toString());

* Close

close 하면됨

```java
socket.close();
```

try-with-resources를 써도 close가능

try (Socket socket = new Socket(host, port)) {&#x20;

&#x20; // Request&#x20;

&#x20; // Response&#x20;

}
