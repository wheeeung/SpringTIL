# oauth

**Open Authorization 개방형 표준 프로토콜**

리소스 소유자를 대신하여 리소스 서버에서 제공하는 자원에 대한 접근 권한을 위임하는 방식

**Resource Owner**

웹 서비스를 이용하려는 유저, 자원을 소유하는 자, 사용자

**Client**

자사 또는 개인이 만든 애플리케이션 서버

**Authorization Server**

권한을 부여(인증에 사용할 아이템을 제공주는)해주는 서버

**Resource Server**

사용자의 개인정보를 가지고있는 애플리케이션(google, facebook, kakao등)회사서버

### oauth 동작방식

직접 사용자가 로그인 하는것이 아닌, 소셜 미디어로 로그인을 할 경우,

client는 resource owner를 대신해 로그인하는데,

이때 필요한 정보를 Resource Server(kakao, naver, ...)에서 얻어 서로 비교해 유효성을 판단한다.

client가 유저의 (로그인)정보/자원(resource)을 Resource Server에 요청해 대신 로그인 하는 것이다.

![image-20220607192444831](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220607192444831.png)