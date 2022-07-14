# CHAPTER 15

### 요청을 비동기적으로 처리하기

@RequestMapping을 설정한 메서드가 Callable이나 스프링 DeferredResult 객체를 반환하면 웹 요청을 비동기적으로 처리한다.

@RequestMapping 메서드가 Callable을 반환하면, 스프링 웹 MVC는 이 Callable을 애플리케이션 스레드에서 실행시켜준다.

@RequestMapping이 DefferredResult를 반환하면, 애플리케이션은 결과를 얻어내기 위해 @RequestMapping을 애플리케이션 스레드에서 실행할 책임을 가지고 있다.

### 타입 변환과 형식화 지원

스프링 Converter 인터페이스를 사용하면 어떤 타입의 객체를 다른 타입의 객체로 쉽게 변환할 수 있다. 스프링 Formatter 인터페이스를 사용하면 어떤 타입의 객체를 그 객체의 지역화된 String표현으로 쉽게 바꾸거나, 지역화된 String 표현을 객체로 쉽게 바꿀 수 있다.

커스텀 Converter 만들기

컨버터는 스프링 Converter<S, T>인터페이스를 구현해야 한다. S(Source)는 컨버터에 전달할 객체의 타입을 말한다. T(target)는 S타입의 객체를 컨버터가 변환해서 내놓을 객체의 타입을 가리킨다.

커스텀 Formatter 만들기

포매터는 T타입의 객체를 표시에 사용할 String 값으로 변환하고, String 값을 구문 분석해서 T타입 객체로 변환한다. 포매터는 스프링 Formatter<T> 인터페이스를 구현한다. T는 포매터가 형식화할 객체의 타입이다.

### 스프링 웹 MVC 파일 업로드 지원

MultipartResolver를 설정하면 스프링 웹 MVC 애플리케이션에서 멀티파트 요청을 처리할 수 있다. 스프링은 웹 애플리케이션에서 다음 MultipartResolver 인터페이스 구현을 바로 사용할 수 있게 제공한다.

멀티파트 요청을 받으면 DispatcherServlet은 설정된 MultipartResolver를 사용해 HttpServletReqeust를 감싸서 MultipartHttpServletRequest 인스턴스로 만든다. 스프링 웹 MVC에서 업로드된 파일은 MultipartFile 객체로 표현된다. 파일 업로드를 처리하는 역할을 하는 컨트롤러는 MultipartHttpServletReqeust에 정의된 메서드를 통하거나 직접 MultipartFile 객체에 접근해서 파일 업로드를 처리한다.