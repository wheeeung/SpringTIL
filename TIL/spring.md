**Spirng Framework는 경량 컨테이너로 자바 객체를 담고 직접 관리**

### ioc

**IOC란 기존 사용자가 모든 작업을 제어하던 것을 특별한 객체에 모든 것을 위임하여 객체의 생성부터 생명주기 등 모든 객체에 대한 제어권이 넘어 간 것을 IOC, 제어의 역전 이라고 합니다.**

## MVC

### model

Model에서는 데이터처리를 담당하는 부분입니다. Model부분은 Serivce영역과 DAO영역으로 나누어짐

### view

View는 사용자 Interface를 담당하며 사용자에게 보여지는 부분입니다. View는 Controller를 통해 모델에 데이터에 대한 시각화를 담당

### controller

Controller에서는 View에 받은 요청을 가공하여 Model(Service 영역)에 이를 전달한다. 또한 Model로 부터 받은 결과를 View로 넘겨주는 역할