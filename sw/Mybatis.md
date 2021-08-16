# MyBatis

:writing_hand: *Assembled by Yunju Jang*

<hr>



✔참고)

- JDBC란?

  - 자바에서 DB와 연동하고 쓰기위해 사용하는 API이다.
  - JDBC만 이용하여 쿼리문을 작성하면 자바소스와 쿼리소스가 겹쳐 복잡하다는 단점이 있다.

  <br/>

  <br/>

## MyBatis

- <b>MyBatis 란?</b>
  - 개발자가 지정한 SQL, 저장 프로시저, 고급 매핑 등을 지원하는 퍼시스턴스 프레임워크이다.
  - JDBC로 처리하는 상당부분의 코드와 파라미터 설정 및 결과 매핑을 대신 해준다.
    - JDBC를 이용하면 1개 클래스에 반복된 코드가 존재하고, 한 파일에 java언어와 sql언어가 함께 있어 재사용 등에 비효율적이다.
    - 이를 개선하여, SQL 명령어와 자바 객체를 매핑해주는 기능을 제공한다.

<br/>

<br/>

- <b>MyBatis 특징</b>
  - 한 두줄의 자바 코드로 DB 연동을 처리한다.
  - SQL 명령어를 자바 코드에서 분리하여 XML 파일에 따로 관리한다.

<br/>

<br/>

- <b>MyBatis 를 사용하는 이유</b>

  - 코드 효율성 향상

    - JDBC는 try-catch 처리, Statement, ResultSet의 데이터 처리를 하기 위해 많은 코드를 써야한다.
    - MyBatis는 SQL Mapper 라이브러리로, 반복 처리 코드 없이 간결하게 사용이 가능하다.

    <br/>

  - SQL문 분리 및 동적 처리

    - JDBC는 개발자가 SQL문을 작성하기 위해 반복적으로 코드를 써야하는 번거로운 작업을 해야하지만, MyBatis의 경우 애노테이션 방식과 XML 방식으로 SQL문을 처리할 수 있다.
    - 간단한 경우에는 앤오테이션 만으로도 처리가 가능하기 때문에 번거로운 작업을 줄일 수 있다.
    - 경우에 따라 SQL문의 변경이 필요한 경우, MyBatis를 활용하여 단편적으로 제어문이나 반복 등의 처리가 가능하여 동적으로 변경이 가능하다.

<br/>

<br/>

## 예상질문❔

Q1) Mybatis란 무엇인가?

A1) 관계형 데이터베이스 프로그래밍을 보다 쉽게 도와주는 프레임워크이다.

<br/>

Q2) MyBatis 를 사용하는 이유는 무엇인가?

A2) JDBC의 SQL문과 자바 언어가 함께 있는 복잡한 구조와 달리 XML 파일에 따로 관리하여 간결하고 재사용 가능하게 하기 때문이다.

<br/>

<br/>

### Reference📖

- https://mybatis.org/mybatis-3/ko/index.html
- https://sjh836.tistory.com/127
- https://developsd.tistory.com/112
- https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=wwwkang8&logNo=220989381100
