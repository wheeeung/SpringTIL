hibernate

hibernate는 자바 언어를 위한 ORM프레임워크이다. JPA의 구현체로, JPA 인터페이스를 구현하며, 내부적으로 JDBC API를 사용한다.

![image-20220709095844295](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220709095844295.png)



hibernate의 장점

생산성

hibernate는 sql을 직접 사용하지 않고, 메서드 호출만으로 쿼리가 수행된다. sql 반복작업을 하지 않아 생산성이 높아진다.

유지보수

테이블 컬럼이 변경되었을 때, 테이블과 관련된 DAO의 파라미터, 결과, sql 등을 대신 수행해준다.

특정 벤더에 종속되지 않음

jpa는 추상화된 데이터 접근 계층을 제공하기 때문에 특정 벤더에 종속되지 않는다.

설정 파일에서 jpa에게 어떤 db를 사용하고 있는지를 알려주기만 하면 얼마든지 db를 바꿀 수 있다.

패러다임 불일치 해결

상속, 연관관계, 객체 그래프 탐색, 비교등 객체와 관계형 데이터베이스와의 패러다임 불일치를 해결할 수 있다.

hibernate의 단점

성능

메서드 호출만으로 쿼리를 수행하는 것은 직접 sql을 작성하는 것보다 성능이 좋지 않다.

세밀함

메서드 호출만으로 db데이터를 조작하기에는 한계가 있다. 이를 보완하기 위해 jpql을 지원한다.