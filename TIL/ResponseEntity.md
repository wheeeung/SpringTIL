# ResponseEntity

### responseEntity

reponseEntity는 http응답을 빠르게 만들어주는 객체이다. 응답으로 변환될 정보를 모두 담은 요소들을 객체로 만들어서 반환해준다.

### 구조

```java
public class ResponseEntity extends HttpEntity {

  private final Object status;
}
```

state만 필드 값으로 가지고 있다. ResponseEntity에서 직접적으로 status code를 지정할 수 있다. 나머지 기능은 httpEntity에 구현되어있다.

```java
public class HttpEntity<T> {
    public static final HttpEntity<?> EMPTY = new HttpEntity<>();
  
  
    private final HttpHeaders headers;
  
    @Nullable
    private final T body;
}
```

ResponseEntity는 HttpEntity를 상속하여 구현한다.

generic타입으로 body가 될 필드 값을 가질 수 있다.

객체안에서 header를 사용할 수 있다.