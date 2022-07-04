# PSA

### Portable Service Abstraction

일관성있는 서비스 추상화이다.

- 공통의 인터페이스로 제어하고 추상화계층을 사용해서 기술을 내부에 숨기고 개발자에게 편의성을 제공해주는 것을 서비스 추상화라고 한다.
- 서비스 추상화로 제공되는 다른 기술 스택으로 간편하게 바꿀 수 있는 확장성을 가지고 있는게 psa이다.

spring에서 제공하는 psa

1. spring web mvc
2. spring transaction
3. spring cache

### spring web mvc

일반 클래스에 @contoller어노테이션을 사용하면 요청을 매핑하는 contoller역할을 수행하는 클래스가 된다.

- 서블릿을 low level로 개발하지 않고도 web mvc를 사용하면 서블릿을 간편하게 개발가능하다.
- httpServlet을 상속받고 doGet(), doPost()를 구현하는 등의 작업을 하지 않아도 된다.

스프링 web mvc는 @controller, @requestmapping같은 어노테이션과 인터페이스, 기술들을 기반으로 사용자가 코드를 거의 변경하지 않고, 웹 기술 스택을 간편하게 바꿀 수 있다.

### spring transaction

transaction 처리를 @transaction어노테이션을 메소드에 붙여서 사용하면 트랜잭션 처리를 간단하게 할 수 있다.

### spring cache

Cache는 JCacheManager, ConcurrentMapCacheManager, EhCacheCacheManager와 같은여러가지 구현체를 사용할 수 있다.

@cacheable어노테이션을 붙여서 구현체를 크게 신경쓰지않아도 된다.