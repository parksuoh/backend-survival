# 2-2 URI & MIME type

* URI

리소스를 식별하는 방법임 (식별자 ID 를 활용함)

URI는 두게로 나뉨

1. URL -> 리소스의위치, 위치변경에 취약함 (URI 와 URL 동의어로 사용됨)
2. URN -> 리소스의 유니크 이름, 잘사용안함

* MIME Type

Content의 종류를 표현한거임

Content-Type 속성을 Headers에 넣어서 전달함.

1. text/plain (이메일에서 자주사용함)
2. text/html (HTML문서)
3. text/css
4. text/javascript
5. application/xml (범용 자기서술적이기 상대적 어려움)
6. application/atom+xml
7. application/json (범용 자기서술적이지 굉장히 어려움)
8. application/dns+json
