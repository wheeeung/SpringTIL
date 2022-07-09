# CHAPTER 3

### 빈 정의 상속

빈 정의를 더 간결화하기 위해 빈 정의가 다른 빈 정의의 설정을 상속할 수 있다.

상속할 수 있는 정보

- 프로퍼티 - <property> 엘리먼트로 설정
- 생성자 인수 - <constructor-arg> 엘리먼트로 설정
- 메서드 오버라이드
- 초기화와 정리 메서드
- 팩토리 메서드

### 생성자 인수 매치하기

스프링 컨테이너가 <constructor-arg> 엘리먼트에 지정한 생성자 인수를 빈 클래스 생성자의 인수와 매치하는 방법

1. 타입으로 생성자 인수 매치시키기
2. 이름으로 생성자 인수 매치시키기

### 프로퍼티 에디터

스프링은 빈 프로퍼티나 생성자 인수를 설정할 때 유용한 여러가지 내장 프로퍼티 에디터를 제공한다.

- CustomClooectionEditor
  - CustomClooectionEditor는 원본 컬렉션 타입을 대상 컬렉션 타입으로 변환할 때 쓰인다. 기본적으로 CustomClooectionEditor는 Set, SortedSet, List타입에 대해 등록되어 있다.
- CustomMapEditor
  - CustomMapEditor는 원본 Map타입을 대상 Map타입으로 변환한다. CustomMapEditor는 SortedMap타입에 대해서만 등록되어있다.
- CustomDateEditor
  - CustomDateEditor는 date타입의 프로퍼티와 생성자 인수를 위한 프로퍼티 에디터이다. CustomDateEditor는 date타입을 문자열로 형식화하거나 날짜/시간을 표현하는 문자열을 파싱해서 Date타입의 객체를 만들 때 쓰이는 사용자 지정 DateFormat을 지원한다.