## ORM이란

Object-relational mapping (객체 관계 매핑) 객체는 객체대로 설계하고, 관계형 데이터베이스는 관계형 데이터베이스대로 설계한다. ORM 프레임워크가 중간에서 매핑해준다.

## JPA란

Java Persistence API

자바의 ORM 기술 표준으로 인터페이스의 모음

### 동작 과정

JPA는 애플리케이션과 JDBC 사이에서 동작한다. 개발자가 JPA를 사용하면, JPA 내부에서 JDBC API를 사용하여 SQL을 호출하여 DB와 통신한다. 즉, 개발자가 직접 JDBC API를 쓰는 것이 아니다.

### 사용이유

sql중심적인 개발에서 객체 중심 개발

생산성

유지보수