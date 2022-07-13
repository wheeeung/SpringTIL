# CHAPTER 9

### 핵심 개념과 인터페이스

스프링 데이터를 사용할 때는 각각의 애플리케이션 도메인 엔티티에 리포지토리 인터페이스를 하나씩 만든다. 리포지토리에는 엔티티의 crud연산과 엔티티 페이지 처리, 정렬을 수행하는 메서드가 있다.

CrudRepository는 Repository를 확장하고 엔티티에 대한 CRUD연산을 수행하는 메서드를 선언한다. save, findById, findAll, deleteById등이 있다.

### 스프링 데이터 JPA

각각의 스프링 데이터 프로젝트는 기반 데이터 스토어가 제공하는 구체적인 기능을 활용하기 위해 각 데이터 저장소에 맞춘 리포지토리 인터페이스를 제공한다.

JPA에는 JpaRepository인터페이스 정의가 있다.

스프링 데이터는 애플리케이션에 정의한 리포지토리 인터페이스마다 각각의 프록시를 생성한다. 프록시는 스프링 데이터에 기본적으로 들어있는 디폴트 리포지터리 구현에 대한 참조를 저장한다.

JPA는 디폴트 리포지터리 구현은 SimpleJpaRepository클래스 이며, 이클래스는 JPA를 통해 관계형db에 접근한다. 프록시는 FixedDepositRepository 인터페이스 메서드 호출을 가로채서 SimpleJpaRepository인스턴스에 위임한다.

@Query를 통해 질의를 명시적으로 지정할 수 있다.

### Querydsl을 사용해 질의 만들기

JPQL질의 대신 JPA Criteria API나 Querydsl을 사용해 프로그램으로 질의를 만들 수도 있다. JPAL 질의와 달리 Criteria API나 Querydsl을 사용해 만드는 질의는 타입안전하다.

Criteria API나 Querydsl은 메타 모델 생성기를 사용해 도메인 엔티티의 특성을 기술하는 메타모델 클래스를 만든다. 메타모델 클래스를 사용해 질의를 생성한다.