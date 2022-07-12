# CHAPTER 8

### 스프링을 사용해 데이터 베이스와 상호 작용하기

스프링은 jdbc 위에 추상 계층을 추가해 데이터베이스와 상호작용을 편리하게 해준다. 스프링은 하이버네이트 간은 ORM 프레임워크로 데이터베이스 상호작용도 단순화시킨다.

### 스프링 jdbc모듈로 애플리케이션 개발

> JdbcTemplate

> JdbcTemplate클래스는 Connection, Statement, ResultSet 객체를 관리하고, jdbc 예외를 잡아서 더 이해하기 좋은 에외로 변환하며, 배치 연산을 수행하는 등의 일을 한다. 개발자는 JdbcTemplate에 SQL을 제공하고, SQL이 실행된 후 결과를 뽑아가기만 하면 된다. JdbcTemplate은 javax.sql.DataSource의 래퍼 역할을 한다. JdbcTemplate인스터스는 보통 데이터베이스 연결을 얻을 때 사용할 javax.sql.DataSource객체로 초기화 된다.

> NamedParameterJdbcTemplate

> JdbcTemplate에서는 ? 위치지정자를 사용해 SQL문 안에 파라미터를 지정한다. NamedParameterJdbcTemplate은 JdbcTemplate 인스턴스를 감싸는 래퍼 클래스로, 이를 사용하면 SQL문 안에서 ? 대신 파라미터 이름을 사용할 수 있다.

> SimpleJdbcInsert

> SimpleJdbcInsert 클래스는 데이터베이스 메타데이터를 활용해 테이블에 로우를 삽입하는 기본 SQL 삽입문을 쉽게 쓸 수 있다.

### 하이버네이트로 애플리케이션 개발

스프링 ORM 모듈은 하이버네이트, 자바 영속성 API, 자바 데이터 오브젝트와 통합할 수 있게 한다. 하이버네이트는 JPA공급자이므로 JPA 어노테이션을 사용해 엔티티 클래스를 데이터베이스 데이블에 매핑한다.

### 스프링을 통한 트랜잭션 관리

스프링 프레임워크는 프로그램을 통한 트랜잭션 관리와 선언적인 트랜잭션 관리 기능을 모두 제공한다. 프로그램을 통해 트랜잭션을 관리할 때는 스프링의 트랜잭션 관리 추상화를 사용해 명시적으로 트랙잭션을 시작, 종료, 커밋한다.

사용

- @Transactional을 사용해 트랜잭션 안에서 실행하는 메서드를 지정한다.
- 클래스 안의 모든 메서드를 트랜잭션 안에서 실행하고 싶으면 클래스에 @Transactional 어노테이션을 설정한다.