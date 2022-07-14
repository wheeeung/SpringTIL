# CHAPTER 16

### 스프링 시큐리티로 웹 애플리케이션 보호

스프링 시큐리티 주요 모듈

| 모듈                    | 설명                                                         |
| ----------------------- | ------------------------------------------------------------ |
| spring-security-core    | 스프링 시큐리티 프레임워크의 핵심 클래스와 인테페이스를 정의한다. 스프링 시큐리티를 사용하는 모든 애플리케이션에 필요한 모듈이다. |
| spring-security-web     | 웹 애플리케이션 보안을 지원한다.                             |
| spring-security-config  | security 스키마나 자바 기반 설정 방식을 사용해 스프링 시큐리티를 설정한다. |
| spring-security-taglibs | JSP페이지에서 표시하는 콘텐트에 보안을 부여하거나 보안 정보에 접근하는 태그를 정의한다. |
| spring-security-acl     | ACL을 사용해 애플리케이션의 도메인 객체 인스턴스를 보호한다. |

웹 요청보안 설정

<http> 엘리먼트에는 애플리케이션의 웹 보안 설정이 들어있다. 스프링 시큐리티 프레임워크는 <http> 엘리먼트를 구문 분석해서 springSecurityFilterChain이름의 빈을 스프링 컨테이너에 등록한다. springSecurityFilterChain 빈은 웹 요청 보안을 처리한다.

<intercept-url> 엘리먼트의 access 속성은 bool값으로 평가되는 SpEL식을 지정한다. SpEL식이 true를 반환하면 사용자는 pattern 속성에 매치하는 URL에 접근할 수 있다. SpEL 식이 false를 반환하면 pattern속성과 매치되는 URL에 대한 접근이 거부된다.                                                                         스프링 시큐리티 프레임워크는 hasRole, hasAnyRole, isAnonymous등 몇 개의 식을 내장하고 있다.

### 자바 기반 설정 방식을 사용해 스프링 시큐리티 설정하기

- 스프링 시큐리티의 WebSecurityConfigurerAdapter를 확장하는 @Configuration 어노테이션이 붙은 클래스를 만든다.
- 스프링 시큐리티의 GlobalMethodSecurityConfiguration을 확장하는 @Configuration 어노테이션이 붙은 클래스를 만든다. 이클래스는 메서드 수준 보안을 설정한다.
- 스프링 시큐리티의 AbstactSecurityWebApplicationInitalizer를 확장하는 클래스를 만든다. 이 클래스는 스프링의 DelegatingFilterProxy 필터를 ServletContext에 등록한다.
- 스프링 시큐리티의 AbstractAnnotationConfigDispatcherServletInitializer를 확장하는 클래스를 만든다. 이 클래스는 DispatcherServlet과 ContextLoaderListener를 ServletContext에 등록한다.

WebSecurityConfigurerAdapter 클래스 사용해 웹 요청 보안 설정

WebSecurityConfigurerAdapter 클래스를 확장하는 클래스에는 @EnableWebSecurity어노테이션이 필요하다.

```java
http.authorizeRequests().antMatchers("/**").hasAnyAuthhority("ROLE_CUSTOMER", "ROLE_ADMIN")
```

이 코드에서 antmatchers 메서드에 매치되는 URL에 ROLE_CUSTOMER나 ROLE_ADMIN 롤을 가진 사용자만 접근할 수 있다는 뜻이다.