# 12-1 CQRS

* CQS -> query(R) 와 Command(CUD) 를 잘 분리해서 활용하자\~&#x20;
* CQRS -> Write Model과 Read Model 분리 , command후 거의 바로 read model을 업데이트 하면 트래픽 비대칭성에 도움
* SSOT(Single Source Of Truth) ->  Write Model 일때 유용
* Materialized View -> RDBMS를 잘알면 Query성능 향상을 위해 좋음. 물리적으로 저장 된후 주기적으로 동기화 됨
* OLTP(Online Transaction Processing) -> 애플리케이션과 긴밀한 관계를 맺는 트랜잭션
* OLAP(Online Analytical Processing) -> 데이터 분석에 집중한것
* Event Sourcing -> 상태변화를 이벤트 연속으로 다룸 (과거를 모아둔것) 주로 CQRS + Event Sourcing을 같이씀
