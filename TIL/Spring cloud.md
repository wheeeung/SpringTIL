# Spring cloud

### spring cloud

마이크로서비스(MSA)의 개발, 배포, 운영에 필요한 아키텍처를 쉽게 구성할 수 있도록 지원하는 프레임워크이다.

분산 시스템상에 필요한 패턴을 표준화 시켜 쉽게 개발할 수 있도록 도와준다.

### spring cloud가 적용된 이상적인 마이크로서비스 환경의 구성

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a0b52db6-5c5c-4052-96d0-36e5367d132a/Untitled.png)

### spring cloud 적용에 사용되는 컴포넌트

spring config

spring cloud config 서버를 두어 사용하면 모든 Spring Boot Application의 환경설정 파일을 한 곳에 저장시킬 수 있고, 해당 서버에 접근하여 환경설정 정보를 가져올 수 있다.

Application의 환경설정 정보를 한 곳에 관리가 가능하고, 환경설정이 바뀌어도 Application 전체를 다시 빌드하지 않아도 된다.

RabbitMQ

AMQP로 만들어져 있으며, Message Queue를 제공한다.

이상적인 마이크로서비스 환경은 마이크로서비스 사이의 통신이 비동기적으로 이루어지는 것이다. RabbitMQ를 사용하면 마이크로서비스들이 외부의 Queue를 통해 메세지를 주고 받을 수 있도록 해서 쉽게 구성할 수 있다.

Eureka

마이크로서비스들의 정보를 레지스트리에 등록할 수 있도록하고 마이크로서비스의 동적인 탐색과 로드밸런싱으로 제공한다.

Zuul

모든 마이크로서비스에 대한 요청을 먼저 받아드리고 라우팅하는 프록시 API Gateway 기능을 수행한다.
