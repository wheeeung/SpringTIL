# CHAPTER 10

### 메일 보내기

스프링은 자바메일 위에 추상화 레이어를 제공해 메일을 쉽게 보낼 수 있다. 스프링에서 메일을 보내려면 xml파일 안에 JavaMailSenderImpl클래스를 설정해야한다. JavaMailSenderImpl클래스는 자바메일 API를 감싸는 래퍼 역할을 한다.

JavaMailSenderImpl 클래스에는 전자우편 서버에 대한 정보를 제공하는 host, port, protocol등의 프로퍼티 정의가 들어있다. javaMailProperties 프로퍼티는 JavaMailSenderImpl인스턴스가 자바메일 Session객체를 만들 때 사용할 설정 정보를 저장한다.

- mail.smtp.auth 프로퍼티값이 true면 SMTP를 사용해 전자우편 서버와 인증한다.
- mail.smtp.starttls.enable 프로퍼티 값이 true면 전자우편 서버와 인증할 때 TLS로 보호되는 연결을 사용한다.

### 캐싱

스프링 캐시 추상화는 개발자가 하부 캐시 구현의 API를 직접 다루지 않도록 해준다.

CacheManager와 Cache 인터페이스는 스프링 캐시 추상화에서 중심적인 역할을 한다. CacheManager 인스턴스는 하부 캐시 솔루션이 제공하는 캐시 매니저를 감싸는 래퍼 역할을 하며, Cache 인스턴스의 컬렉션을 관리한다. Cache 인스턴스는 하부 캐시를 감싸며, 하부 캐시와 상호작용하는 메서드를 제공한다.

캐시 어노테이션

- @Cacheable
  - 메서드에 @Cacheable을 설정하면 메서드의 반환값을 캐시에 넣는다.
- @CacheEvict
  - 어떤 메서드가 호출되면 캐시에 있는 데이터를 모두 비울 때 @CacheEvict를 설정한다.
- @CachePut
  - 항상 메서드를 호출해서 반환값을 캐시에 넣어야한다는 의미의 @CachePut 어노테이션을 지원한다.