# 2-3 Collection pattern

* Post ID는 리소스의  ID가 아님
* 그룹명은 복수형으로사용 개별 아이템도 왠만하면 복수형

ex) /posts/1

* 특정 상황에 디렉터리처럼 구성 가능

ex) /posts/{post\_id}/comments&#x20;

/comments?post\_id={post\_id}

/posts/{post\_id}/comments/{id}&#x20;

/comments/{id} -> 간단한 삭제 요청작업등에 오히려좋음

/posts/{id}/edit -> REST API의 경우 /items/{id} 쪽으로 쓰는거 추천&#x20;

* 그룹이 아닌경우는 단수 사용가능

ex) /session (가능)  /sessions/1 (안됨)

/edits/commnet -> /pages/edit-post (가 좋음)
