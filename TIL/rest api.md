# rest api

### rest api

rest api란 rest 아키텍쳐 스타일을 지키는 api를 말한다.

### rest

rest는 Representational state transfer의 약어로서 부수적인 레이어나 셰션 관리를 추가하지 않고도 HTTP프로토콜로 데이터를 전달하는 프레임워크이다.

### 특징

- 모든 Resource는 클라이언트가 바로 접근할 수 있는 URI가 존재한다.
- 웹 어플리케이션은 클라이언트의 상태에 대한 정보를 보관하지 않는다.
- HTTP 요청은 완전히 독립적이다.
- 클라이언트가 요청할 때마다 필요한 모든 정보를 준다.
- 모든 Resource는 일반적 HTTP 인터페이스인 GET, POST, PUT, DELETE로 접근해야한다.

### mvc controller와 rest controller의 차이

mvc controller는 view 기술을 사용하고 rest controller는 객체를 반환하면 객체 데이터가 json/xml 형식의 http응답에 직접 작성됩니다.