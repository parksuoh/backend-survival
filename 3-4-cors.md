# 3-4 CORS

* &#x20;CORS 란

1. 동일 출처 정책 -> 웹브라우저에서 출처가다르면 접근할 수 없게 하는 보안정책이다.
2. JSONP -> \<script>테그는 동일출처가 아니어도 실행된다.
3. Access-Control-Allow-Origin -> 헤더에 “Access-Control-Allow-Origin” 을 추가하면 브라우저에서 cors에러를 피할수있다.

* @CrossOrigin -> 스프링에서 어노테이션을 붙여주면 “Access-Control-Allow-Origin”을 설정할 수 있다.
