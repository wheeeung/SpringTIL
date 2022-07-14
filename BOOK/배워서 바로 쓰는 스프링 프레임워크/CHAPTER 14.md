# CHAPTER 14

### 스프링 웹 MVC로 RESTful 웹 서비스 개발하기

REST(Representational State Transfer 표현 상태 전송)는 애플리케이션이 URI(Uniform Resource Identifier 고유 자원 식별자)를 통해 유일하게 식별하는 자원을 정의하는 아키텍처 스타일이다.   REST-스타일 애플리케이션의 클라이언트는 요청이 매핑된 URI에 HTTP GET, POST, PUT, DELETE메서드를 보냄으로써 자원과 상호작용한다.

REST 아키텍처 스타일을 따르는 웹서비스를 RESTful 웹 서비스라고 부른다. 클라이언트는 RESTful 웹서비스에 HTTP요청을 보냄으로써 노출된 데이터에 대한 CRUD연산을 수행할 수 있다. 클라이언트와 RESTful 웹서비스는 데이터의 표현을 교환하며, 이표현은 XML, JSON형식 간단한 문자열 또는 HTTP 프로토콜이 지원하는 다른 MIME 타입이 될 수 있다.

### 스프링 웹 MVC를 사용해 RESTful 웹 서비스 구현하기

- 웹 서비스가 노출할 자원을 식별한다.
- 식별한 자원에 대한 URI를 지정한다.
- 각 자원에 수행할 수 있는 연산을 식별한다.
- 식별한 연산에 대한 HTTP 메서드를 매핑한다.

JSON

텍스트 기반 데이터 표기법으로 애플리케이션들이 구조화딘 데이터를 서로 교환할 때 쓰인다. XML보다 더 간결하게 표현가능하다.

### HttpMessageConverter로 자바 객체를 HTTP요청이나 응답으로 변경하거나, 반대 방향으로 변경하기

스프링은 HttpMessageConverter를 사용해 여러 변환을 수행한다.

- 메서드 인수에 @RequestBody를 설정하면 슾링은 HTTP 요청 본문을 메서드 인수의 자바 타입으로 변환한다.
- 메서드에 @ResponseBody를 설정하면 스프링은 메서드가 반환한 자바 객체를 HTTP 응답 본문으로 변환한다.
- 메서드의 반환 타입이 HttpEntity나 ResponseEntity라면, 스프링은 메서드가 반환한 자바 객체를 HTTP응답 본문으로 변환한다.
- RestTemplate 클래스가 제공하는 메서드에 전달되거나 반환되는 객체는 각각 HTTP 요청 본문으로 변환되거나 HTTP 응답 본문으로 변환된다.

HttpMessageConverter 구현

- StringHttpMessageConverter
- FormHttpMessageConverter
- MappingJackson2HttpMessageConverter
- MarshallingHttpMessageConverter

### @Pathvariable, @MatrixVariable 어노테이션

@PathVariable은 URI 템플릿 변수의 값을 메서드 인수에 대입하기 위해 @RequestMapping 메서드에 사용할 수 있는 메서드 인수 수준의 어노테이션이다.

@RequestMapping 어노테이션에 URI템플릿을 지정할 수 있다. URI 템플릿에는 변수이름(중괄호로 묶어서 표시)이 있고, 이 변수의 값은 실제 요청 URI로부터 만들어진다.

@MatrixVariable은 요청 URI에 이름-값 쌍으로 나타나는데, 이런 변수의 값을 메서드 인수에 대입할 수 있다.