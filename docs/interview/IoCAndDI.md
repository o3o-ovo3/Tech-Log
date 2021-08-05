# IoC란?

:writing_hand: *Assembled by Yunju Jang*



<hr>


- <b>직무 면접에서 받은 질문 정리 🙋‍♀️</b>
  - (Spring framework에 대해) IoC란 무엇이라고 생각하는지?
    - 내 대답 : 스프링 프레임워크는 애플리케이션 제작에 있어 개발자가 편리하게 코드를 작성할 수 있도록 전체적인 흐름을 제공한다. 개발자는 그 흐름에 맞추어 코드를 작성하는데, 이거을 제어의 역행이라고 한다. 스프링 프레임워크를 사용하지 않을 때에는 개발자가 애플리케이션의 전체적인 흐름을 쥐고 처음부터 끝까지 코드를 작성하게 된다.

<br/>

<br/>

## IoC (Inversion of Control)

- <b>제어의 역전(역행)이란?</b>
  - 제어권이 역전된 것을 뜻한다.
    - 예전에는 의존 관계의 제어를 개발자가 직접 해주었다.
    - 그러나 현재는 제어권이 컨테이너로 넘어갔고, 객체의 생성부터 생명주기의 관리까지 객체에 대한 제어권이 바뀐 것을 IoC라고 한다.

<br/>

- 예시)

  ``` java
  import org.springframework.stereotype.Repository;
  
  @Repository
  public class BookRepository{
      
  }
  ```

  - 위와 같은 Repository 객체가 있을 때, 과거에는 아래와 같이 개발자가 직접 제어했다.

    ``` java
    import org.springframework.stereotype.Service;
    
    @Service
    public class BookService{
        BookRepository bookRepository = new BookRepository();
    }
    ```

    - BookRepository 클래스를 직접 인스턴스로 의존관계를 나타내고 있다.
    - 즉, 개발자가 직접 객체를 제어하여 BookService가 BookRepository에게 의존하고 있음을 클래스를 통해 표현하고 있다.

  <br/>

  - 그러나 제어권이 컨테이너로 넘어갔고, 객체의 생성과 생명주기의 관리까지 할 수 있기 때문에 아래와 같은 방식으로 바뀐다.

    ``` java
    @Service
    public class BookService{
        BookRepository bookRepository;
        
        @Autowired
        public BookService(BookRepository bookRepository){
            this.bookRepository = bookRepository;
        }
    }
    ```

    - 컨테이너에 의해 생성한 객체를 사용만 하는 코드이다.
    - BookRepository가 스프링 컨테이너에게 관리되고 있는 Bean이라면, @Autowired를 통해 객체를 주입 받을 수 있게 된다. (DI)
    - 이것은 개발자가 직접 객체를 관리하지 않고 스프링 컨테이너가 직접(제어) 객체를 생성하여 해당 객체에 주입시켜준 것이다.

<br/>

<br/>

- <b>IoC 컨테이너란?</b>
  - 핵심 Interface : BeanFactory
  - Application Component 중앙 저장소
  - Bean 설정 소스로부터 빈 정의를 읽어들여 빈을 구성하고 제공하는 역할을 한다.
  

<br/>

<br/>

- <b>Spring IoC 컨테이너</b>
  - ApplicationContext 인터페이스를 구현한 클래스의 오브젝트
  - ApplicationContext는 BeanFactory에 여러가지 기능을 추가한 것
  - 빈 인스턴스를 생성
  - 의존 관계 설정
  - 빈 제공

<br/>

<br/>

- <b>DI (의존성 주입)이란? </b>

  - 각 클래스 간의 의존 관계를 Bean 설정 (xml 파일) 정보를 바탕으로 컨테이너가 자동으로 연결해주는 것을 말한다.

  - IoC 프로그래밍 모델을 구현하는 방식 중의 하나이다.

  - IoC가 범용적인 의미이기 때문에 스프링이 제공하는 기능의 특징을 명확하게 설명하지 못한다.

    - 그렇기 때문에 스프링이 제공하는 IoC 방식의 핵심을 표현하기 위해 의존성 주입이라는 용어를 사용하기 시작했다. (DI가 스프링에서 시작된 개념은 아님)

  - 핵심은 <b>외부에서 주입되는 동적인 의존 관계</b>이다.

    >Spring DI의 3가지 조건
    >
    >- 클래스 모델이나 코드에는 의존 관계가 드러나지 않는다.
    >- 런타임 시점의 의존 관계는 컨테이너나 팩토리 같은 존재가 결정한다.
    >- 의존 관계는 사용할 오브젝트에 대한 레퍼런스를 외부에서 제공(주입) 해 줌으로써 만들어진다.

  - 클래스 간의 관계는 런타임환경에서 동적으로 결정된다. 그렇기 때문에 유연한 코드로 인해 개발의 어려움이 적다.

<br/>

<br/>

- <b>IoC의 장점</b>
  - 객체를 관리해주는 독립적인 존재 (컨테이너) 와 그 외 구현하고자 하는 부분으로 각각 관심을 분리하고, 서로의 역할을 충실히하면서 <b>변경에 유연한 코드</b>를 작성할 수 있는 구조
    - 즉, 다른 컨테이너에게 제어에 대한 역할을 위임
    - 위임된 객체에 대해 신경쓰지 않고, 역할과 책임에 대한 신경만 쓴다.
    - 이를 통해 변경에 유연한 코드 구조를 가져올 수 있다.

<br/>

<br/>

### Reference📖

- https://csy7792.tistory.com/148
- https://biggwang.github.io/2019/08/31/Spring/IoC,%20DI%EB%9E%80%20%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C/
- https://redcoder.tistory.com/198