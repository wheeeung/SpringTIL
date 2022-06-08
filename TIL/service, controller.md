# service, controller

## service

controller에서 데이터를 전달 받아 가공함

@service 어노테이션 사용

## controller

시스템으로 들어오는 요청과 응답을 담당함

@restcontroller사용

### restcontroller와 controller 차이

@Controller는 주로 View를 반환하기 위해 사용합니다.

@RestController는 Spring MVC Controlle에 @ResponseBody가 추가된 것입니다. RestController의 주용도는 Json 형태로 객체 데이터를 반환하는 것입니다. 최근에 데이터를 응답으로 제공하는 Restful API를 개발할 때 주로 사용

@requestmapping 들어온 요청을 특정 메서드와 매핑하기 위해 사용하는 것

get, delete, post, putmapping이 requestmapping에 복잡함을 해결

@pathvariable url에 값을 받음

@requestbody dto에 값을 받음 json형태

## dao

DAO는 DB의 data에 접근하기 위한 객체로 직접 DB에 접근하여 데이터를 삽입, 삭제, 조회 등 조작할 수 있는 기능을 수행한다.

## dto

DTO는 계층간(Controller, View, Business Layer) 데이터 교환을 위한 자바 빈즈(Java Beans)를 의미한다.

DTO(Data Transfer Object)는 데이터 전송(이동) 객체라는 의미를 가지고 있다.