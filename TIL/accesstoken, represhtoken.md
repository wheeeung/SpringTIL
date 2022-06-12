# accesstoken, represhtoken

### accesstoken

private resource에 접근하는 rest api에 대한 모든 요청에 대한 토큰이 포함되어 있는지, 또 해당 토큰이 유효한지의 여부를 검증함으로써 인증 절차를 수행할 때 사용하는 토큰이다.

access token은 수명이 있어 재발급을 받아야한다.

refresh token으로 다시 로그인 하지 않고 발급 받을 수 있다.

### represh token

post 방식으로 client_id값, client_secret값, refresh_token값, grant_type값을 포함하여 authorizationserver로 보내게 되면 authroizationserver는 새로운 access token을 발급해준다.

![image-20220613085006552](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220613085006552.png)