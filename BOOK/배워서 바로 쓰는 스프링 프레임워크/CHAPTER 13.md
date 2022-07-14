# CHAPTER 13

### @ModelAttribute 어노테이션을 사용해 모델 추가하고 가져오기

스프링의 Model 객체에 속성을 저장하고 싶을 때는 메서드에 @ModelAttribute를 설정하고, Model 객체에서 속성을 읽고 싶을 때는 메서드 인수에 @ModelAttribute를 설정한다.

메서드에 @ModelAttribute를 설정하면, 메서드는 하나 이상의 모델 속성을 Model 객체에 추가한다. 메서드 인수에 @ModelAttribute를 설정하면, Model 객체에서 모델속성을 읽어 메서드 인수에 대입한다.

### @SessionAttribute 어노테이션을 사용해 모델 속성 캐싱하기

@ModelAttribute를 설정한 모델 속성을 HttpSession세션에서 찾을 수 없을 때만 @ModelAttribute를 설정한 메서드를 호출한다. 메서드 인수에 @ModelAttribute를 설정한 경우에도 HttpSession에서 해당 모델 속성을 찾을 수 없을 때만 새로운 모델 속성 인스턴스를 생성한다.

### 스프링의 데이터 바인딩 지원

폼을 스프링 웹 MVC 애플리케이션에서 제출하면 요청에 들어있는 요청 파라미터에 폼 기반 객체로 사용 중인 모델 속성이 자동으로 설정된다. 폼 지원 객체를 요청의 요청 파라미터로 자동 설정하는 처리 과정을 데이터 바인딩이라고 한다.

WebDataBinder

폼 지원 객체에서 적정한 자바빈 스타일 세터 메서드를 찾기 위해 요청 파라미터 이름을 사용한다. WebDatabinder는 찾은 자바빈 스타일 세터 메서드를 호출하면서 요청 파라미터 값을 세터 메서드의 인수로 전달한다.

WebDataBinder 인스턴스 설정하기

- @InitBinder를 설정한 메서드를 컨트롤러 클래스에 정의한다.
- WebBindingInitializer 구현을 웹 애플리케이션 컨텍스트 XML 파일에 설정한다.
- @ControllerAdvice를 설정한 클래스 안에 @InitBinder를 설정한 메서드를 선언한다.