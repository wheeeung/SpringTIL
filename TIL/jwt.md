# jwt

json web token

토큰 기반 인증

![image-20220607192322820](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220607192322820.png)

### 인증방식

1. 클라이언트가 아이디와 비밀번호를 서버에게 전달하며 인증을 요청한다.
2. 서버는 아이디와 비밀번호를 통해 유효한 사용자인지 검증하고, 유효한 사용자인 경우 토큰을 생성해서 응답한다.
3. 클라이언트는 토큰을 저장해두었다가, 인증이 필요한 api에 요청할 때 토큰정보와 함께 요청한다.
4. 서버는 토큰이 유효한지 검증하고, 유효한 경우에는 응답을 해준다.