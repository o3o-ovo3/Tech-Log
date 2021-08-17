# Mybatis, JPA, Hibernate 비교

:writing_hand: *Assembled by Yunju Jang*

<hr>



✔ 참고)

- SQL Mapper

  - 직접 SQL문을 작성해 DB를 접근하는 것이다.
  - Mybatis가 SQL Mapper에 해당된다.

  <br/>

- ORM (Object Relational Mapping)

  - DB의 데이터를 객체로 매핑시켜 데이터를 접근할 수 있는 것이다.
  - ORM을 사용하면 SQL을 작성하지 않고도 메소드를 사용해 데이터를 조작할 수 있다.
  - JPA, Hibernate 등이 해당한다.

  <br/>

  <br/>

## Mybatis, Hibernate, JPA

- <b>Mybatis</b>
  - 자바에서 DB에 접근할 수 있도록 JDBC라는 라이브러리를 제공한다.
    - JDBC는 사용할 때마다 connection을 생성해주어야 하고, 중복되는 코드가 많다는 단점이 있다.
  - JDBC를 사용하기 쉽게 만들어주는 것이 Mybatis이다.
  - SQL Mapper로써, JDBC로 처리하는 부분의 일부를 코드와 파라미터 설정으로 매핑을 대신 해준다.
    - 소스코드와 sql을 분리할 수 있다.

<br/>

<br/>

- <b>JPA (Java Persistent API)</b>
  - Java ORM 기술에 대한 API 표준 명세로, 이 또한 자바에서 제공하는 API이다.
  - 자바 애플리케이션에서 RDBMS를 사용하는 방식을 정의한 인터페이스이다.
  - CRUD 쿼리를 자동으로 생성해주고, Entity에 속성만 추가해준다면 쿼리를 건들 필요가 없다.

<br/>

<br/>

- <b>Hibernate</b>
  - Hibernate는 JPA의 구현체이다.
  - 테이블 생성, 변경, 관리가 쉽고 빠른 개발이 가능하다.

<br/>

<br/>

<br/>

## 예상질문❔

Q1) Mybatis, JPA, Hibernate의 차이는 무엇인가?

A1) Mybatis는 JDBC를 이용하여 DB에 복잡하지 않게 접근하는 것을 돕는 SQL Mapper이다. JPA는 JDBC와 마찬가지로 자바에서 제공하는 API로 객체와 데이터를 매핑시키는 ORM 방식이다. Hibernate는 이 JPA를 구현한 구현체 중 하나이다.

<br/>

<br/>

### Reference📖

- https://velog.io/@leeinae/Spring-Mybatis-JPA-Hibernate-%EB%B9%84%EA%B5%90
- https://gmlwjd9405.github.io/2018/12/25/difference-jdbc-jpa-mybatis.html
