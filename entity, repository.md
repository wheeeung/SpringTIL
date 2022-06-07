# entity, repository

## entity

데이터베이스(Database, DB) 에 쓰일 필드와 여러 엔티티간 연관관계를 정의

어노테이션

**@Entity**

: 클래스 위에 선언하여 이 클래스가 엔티티임을 알려준다. 이렇게 되면 JPA에서 정의된 필드들을 바탕으로 데이터베이스에 테이블을 만들어준다.

**@Builder**

: 해당 클래스에 해당하는 엔티티 객체를 만들 때 빌더 패턴을 이용해서 만들 수 있도록 지정해주는 어노테이션이다. 이렇게 선언해놓으면 나중에 다른 곳에서 Board.builder(). {여러가지 필드의 초기값 선언 }. build() 형태로 객체를 만들 수 있다.

**@AllArgsConstructor**

: 선언된 모든 필드를 파라미터로 갖는 생성자를 자동으로 만들어준다.

**@NoArgsConstructor**

: 파라미터가 아예없는 기본생성자를 자동으로 만들어준다.

**@Getter**

: 각 필드값을 조회할 수 있는 getter를 자동으로 생성해준다. 예를들어 다른 파일에서 Board 객체의 title값을 얻고 싶다면 getTitle() 메서드를 정의해서 해당 객체의 title값을 얻어오게 되는데, 해당 메서드를 굳이 작성하지 않아도 자동으로 생성해주는 것이다.

**@Id, @GeneratedValue**

: 해당 엔티티의 주요 키(Primary Key, PK)가 될 값을 지정해주는 것이 @Id 이다. @GeneratedValue는 이 PK가 자동으로 1씩 증가하는 형태로 생성될지 등을 결정해주는 어노테이션이다.

**@ManyToOne**

: 해당 엔티티와 다른 엔티티를 관계짓고 싶을 때 쓰는 어노테이션이다. ManyToOne이라고 부르는 이유는 Writer 입장에서 Board는 여러 개가 될 수 있기 때문에 Writer : Board = 1 : N 관계가 되기 때문이다.

**@JsonIgnoreProperties**

무시할 속성이나 속성 목록을 표시하는 데 사용

무한 참조를 막기위해 사용했음

## repository

Entity에 의해 생성된 DB에 접근하는 메서드들을 사용하기 위한 인터페이스

jpa를 상속 받게해 기본적인 crud를 할 수있다.