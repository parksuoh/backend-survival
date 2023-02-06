# 2-1 REST API

프론트엔드와 백엔드 연결방법으로 REST API를 사용한다.



### API 란 무엇이냐?

컴퓨터와 컴퓨터 프로그램 사이의 연결!

#### Interface

* Communication -> 서로간에 소통하기위함
* Specification -> 명세
* Information Hiding (Principle) -> 정보은닉 ->어딘가 숨김
* Encapsulation (Technique) -> 캡슐화 -> 한곳에 모아둠 이러면 내부와 외부가 생김 (정보은닉의 방법)
* Implementation -> 따로분리



### REST란무엇이냐?

REST라는방식 (표현 상태 변형)

네트워크 중심 소프트웨어 아키텍쳐 스타일!



1️.**Starting with the Null Style**

2.**Client-Server**

3\. **Stateless**

4️.**Cache**

5️.**Uniform Interface → 핵심!**

1. 클라이언트와 서버간의 정해진 형식을사용
2. 일반적 공학의 원칙을 웹에 적용 -> 심플 가시적
3. 구현이 분리가 된다 -> 독립적
4. 규칙이 정해져있어서 효율성이 떨어질수도있다.
5. 대규모의 하이퍼미디어 전송에 아주 효과적이다.
6. **필딩 제약 조건**

* Four Interface Constraints

리소스 식별 (URI등을 이용)

표현을 통한 리소스 조작

자기서술적인 메시지여야함 (REST 에서 까다로움) -> 여러레이어 프로그램내에서 나눠질수있음 그안에서 처리되거나 변환할수있어야함 그럴려면 메시지가 뭔질 알아야 처리가능 (ex. key value)&#x20;

HATEOAS  (REST 에서 까다로움) -> 구현은 쉬움 잘안함

* 아키텍처 요소(5.2)에서 리소스와 표현을 구분

Resource -> 추상 모든시간에 통영되는 엔티티 집합.

Representation -> 표현 data + metadata + Meta-metadata&#x20;



* URI 파트(6.2)에서 리소스에 대해 다시 강조

리소스는 서버에 저장된 무언가가아님&#x20;

리소스, 표현, 실제데이터 등은 구분

* 아키텍처 데이터 뷰(5.3.3)에서 HATEOAS에 대해 언급.

하나의 상태를 다음 상태로 변환하기위한 선택 -> representation에 있음 (ex. 웹에서 뭐 누르면 바뀜)

선택 가능한 상태전환이 포함되어야함 (ex.하이퍼 링크)

대부분은 효율 문제 때문에 API문서를 활용해 처리





7\.  **Layered System**

8\. **Code-On-Demand**



ㄴREST 는 API를 위한 아키텍처 스타일은 아님웹에 특화된 방법임 근데 API만들때 유용함

Level 1 (Resources) Level 2 (HTTP Verbs)정도만 만족해도 REST API라고 한다.



