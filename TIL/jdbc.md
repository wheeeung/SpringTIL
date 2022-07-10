# jdbc

### Java Database Connectivity

자바 프로그래밍 언어와 다양한 데이터베이스 sql또는 테이블 형태의 데이터 사이에 독립적인 연결을 지원하는 표준이다.

자바를 이용한 db접속과 sql문장의 실행, 그리고 실행 결과로 얻어진 데이터의 핸들링을 제공하는 방법과 절차에 관한 규약이다.

sql과 프로그래밍 언어의 통합 접근 중 한 형태이다.

### 필요한 이유

db학습시 sql을 이용해서 db를 직접 조작했는데 프로그램이 대신 이 일을 할 수 있게 만들어주어야 하는데 이때 jdbc를 사용한다.

### jdbc클래스의 생성관계

드라이버 로딩시 DriverManager라는 객체가 갖고 있는 메서드를 이용해서 드라이버를 로딩한다. 그래서 DriverManager 객체를 이용해서 Connection 인스턴스를 얻어내고, Connection 인스턴스를 통해서 statement객체를 얻어내고, statement객체를 통해 resultSet을 얻어낸다. 닫을 때는 열때와 반대순서로 닫아주어야한다.