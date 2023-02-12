# 2-5 Spring Web MVC로구현

* @RequestMapping -> 클라이언트로부터 요청 어노테이션 이다. 컨트롤러 클레스 위에 붙여준다.

1. @GetMapping -> GET요청시 함수위에 붙여주는 어노테이션이다
2. @PostMapping -> POST요청시 함수위에 붙여주는 어노테이션이다
3. @PatchMapping -> PATCH요청시 함수위에 붙여주는 어노테이션이다
4. @DeleteMapping -> DELETE요청시 함수위에 붙여주는 어노테이션이다
5. @PathVariable -> path에 넣어준 값을 함수에 알려주기위한 어노테이션이다.

* @RequestBody -> 클라이언트 요청시 body값을 알려주기위한 어노테이션이다.
* @ExceptionHandler -> error발생시 처리를 해주는 어노테이션이다.
* @ResponseStatus -> 서버에서 응답해줄시 response status를 지정해줄수있는 어노테이션이다.
