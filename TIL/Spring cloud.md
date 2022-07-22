# Spring cloud

### spring cloud

마이크로서비스(MSA)의 개발, 배포, 운영에 필요한 아키텍처를 쉽게 구성할 수 있도록 지원하는 프레임워크이다.

분산 시스템상에 필요한 패턴을 표준화 시켜 쉽게 개발할 수 있도록 도와준다.

### 중요 컴포넌트

spring config

spring cloud config 서버를 사용해 spring boot application의 환경설정 파일을 한 곳에 저장, 해당 서버에 접근하여 환경설정 정보를 가져온다.

hystrix

장애상황을 견딜 수 있도록 해주는 spring cloud component이다.

특징

- 다른 서비스 실패에 따른 서비스 지연 또는 실패방지
- 분산 시스템의 복잡한 연쇄실패 방지
- 빠르게 실패하고 빠르게 복구
- real-time에 유사한 모니터링과 알람

Ribbon Client

Netfix OSS 라이브러리

클라이언트 측 로드밸런서

RestTemplate 대신 FeignClient를 사용하여 Ribbon 기능 사용

여러 서버를 라운드로빈 방식의 부하 분산 기능 제공