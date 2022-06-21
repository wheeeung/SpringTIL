# spring-test, junit

### junit

전체 프로젝트를 실행하지 않고 단위 코드 테스트를 할 수 있게 해주는 라이브러리이다.

### spring-test

junit을 확장한 스프링의 테스트 라이브러리이다.

### junit지원 어노테이션

@Test

테스트를 수행하는 메소드를 지정한다. junit에서는 각각의 테스트가 서로 영향을 주지 않고 독립적으로 실행되는 것을 지향한다.

@Ignore

테스트를 실행하지 않도록 한다.

@Before / @After

테스트 메소드가 실행되기전, 후로 항상 실행되는 메소드를 지정한다.

@BeforeClass / @AfterClass

각각의 메소드가 아닌 해당클래스에서 딱 한번만 수행되는 메소드이다.

### Spring-test 어노테이션

@RunWith(SpringJUnit4ClassRunner.class)

ApplicationContext를 만들고 관리하는 작업을 할 수 있도록JUnit의 기능을 확장해준다. Spring-test라이브러리로 확장된 JUnit은 컨테이너 기술을 사용해 싱글톤으로 관리되는 객체를 모든 테스트에 사용할 수 있다.

@ContextConfiguration(locations=”파일 위치”)

스프링 빈 설정 파일의 위치를 지정할 수 있다. 별도로 컨테이너를 추가하지 않고 빈을 등록해둔 파일을 지정해 컨테이너에서 사용할 수 있도록 해준다.