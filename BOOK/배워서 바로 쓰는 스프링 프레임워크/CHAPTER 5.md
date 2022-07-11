# CHAPTER 5

### 빈의 초기화와 정리 로직 커스텀화

빈 프로퍼티가 설정된 후 스프링 컨테이너가 빈을 완전히 초기화하기 전에 커스텀 추기화 로직을 실행하려면 초기화 메서드의 이름을 <bean>엘리먼트의 init-method 속성값으로 지정한다.

### 정리 메서드와 프로토타입 빈

프로토타입 스코프 빈의 경우 스프링 컨테이너가 destroy-method 속성을 무시한다. 왜냐하면 applicationContext에서 프로토타입 빈을 얻어낸 객체가 자신이 사용한 프로토타입 스코프 빈의 해제 메서드를 명시적으로 호출할 책임을 지도록 스프링 컨테이너가 원하기 때문이다.

### BeanPostProcessor

스프링 애플리케이션에서 어떤 빈 인스턴스가 다른 빈에 의존 관계로 주입되기 전에 제대로 설정됐는지 검증하고 싶으로때 BeanPostProcessor구현을 사용한다.

### BeanFactoryPostProcessor를 사용해 빈 정의 변경

빈 정의를 변경하고 싶은 클래스는 BeanFactoryPostProcessor인터페이스를 구현하면 된다. BeanFactoryPostProcessor는 스프링 컨테이너가 빈 정의를 로드한 다음, 빈 인스턴스를 만들어내기 전에 실행되고, XML 파일에 정의된 다른 모든 빈이 생성되기 전에 생성된다.