# Oracle과 MySQL 차이

:writing_hand: *Assembled by Yunju Jang*



<hr>


- <b>직무 면접에서 받은 질문 정리 🙋‍♀️</b>
  - Oracle과 MySQL의 차이
  - 함수들의 차이

<br/>

<br/>

## Oracle

- <b>Oracle의 특징</b>
  - 성능이 좋고 기능이 많으며 비용이 많이 든다.
  - 대규모 데이터베이스를 지원한다.
  - 고성능 트랜잭션 처리를 제공하여 속도가 빠르다.
  - SQL 문을 실행하는 가장 효율적인 방법을 선택한다.
    - 비용을 최소화하기 위해 테이블과 인덱스를 분석한다.

<br/>

<br/>

## MySQL

- <b>MySQL 특징</b>

  - 오픈소스로 무료로 사용 가능하다.

  - top N개의 레코드를 가지고 오는 케이스에 특화되어 있다.

  - Nested Loop Join만 지원한다.

    > Nested Loop Join
    >
    > - 바깥 테이블의 처리 범위를 하나씩 접근하면서 추출된 값으로 안쪽 테이블을 조인하는 방식
    >   - 중첩 루프문과 동일한 원리
    >   - 좁은 범위에 유리
    >   - 순차적 처리

  - 복잡한 알고리즘은 가급적 지원하지 않는다.

  - 문자열 비교에서 대소문자를 구분하지 않는다.

  - 간단한 처리 속도를 향상시키는 것을 추구한다.

  

<br/>

<br/>

### <mark>Oracle과 MySQL 비교</mark>

- <b>함수의 차이</b>

  - 컬럼값이 NULL이면 다른 값으로 표시해주는 함수

    > Oracle
    >
    > - SELECT <b>NVL(USER_ID, ' ')</b> FROM TABLE;
    >
    > MySQL
    >
    > - SELECT <b>IFNULL(USER_ID, ' ')</b> FROM TABLE;

    <br/>

  - 현재 날짜와 시간을 확인하는 함수

    >Oracle
    >
    >- SELECT <b>SYSDATE(REG_DATE, 'YYYYMMDD HH24MISS')</b> FROM DUAL;
    >
    >MySQL
    >
    >- SELECT <b>DATE_FORMAT(REG_DATE, '%Y%m%d%H%i%s')</b> FROM DUAL;

    <br/>

  - 요일변환의 숫자범위

    > Oracle
    >
    > - 일, 월, 화, 수, 목, 금, 토를 1, 2, 3, 4, 5, 6, 7로 인식
    > - SELECT TO_CHAR(SYSDATE, 'D') FROM DUAL;
    >   - 결과값: 오늘이 수요일인 경우 4를 반환
    >
    > MySQL
    >
    > - 일, 월, 화, 수, 목, 금, 토를 0, 1, 2, 3, 4, 5, 6 으로 인식
    >   - SELECT DATE_FORMAT(NOW(), '%w') FROM DUAL;
    >   - 결과값: 오늘이 수요일인 경우 3을 반환

    <br/>

  - 문자와 문자를 합치는 방법

    > Oracle - '||' 사용
    >
    > - SELECT USER_ID <br/>FROM TABLE<br/>WHERE USER_ID LIKE '%' <b>||</b> 'kim' <b>||<b/> '%'
    >
    > MySQL  - CONCAT() 함수 사용
    >
    > - SELECT USER_ID<br/>FROM TABLE<br/>WHERE USER_ID LIKE <b>CONCAT('%', 'kim', '%')</b>

    <br/>

  - 형 변환 함수

    > Oracle - TO_CHAR, TO_NUMBER 사용
    >
    > - SELECT <b>TO_CHAR(632)</b> FROM DUAL;
    >
    > MySQL - CAST 사용
    >
    > - SELECT <b>CAST(1234 AS CHAR)</b> FROM DUAL;

    <br/>

  - 페이징 처리

    > Oracle
    >
    > - SELECT * <br/>FROM (SELECT <b>ROWNUM</b>, A.* <br/>			FROM (SELECT * FROM TABLE) A)<br/> WHERE <B>ROWNUM BETWEEN 0 AND 10</b>;
    >
    > MySQL
    >
    > - SELECT * <br/>FROM TABLE <b>LIMIT 0, 10</b>;

    <br/>

  - 시퀀스 사용 시 다음 번호 불러오는 방법

    > Oracle
    >
    > - <b>.NEXTVAL</b>
    >
    > MySQL
    >
    > - <b>.CURRVAL</b>

<br/>

<br/>

<br/>

### Reference📖

- https://junghyun100.github.io/OracleVsMySql/
- https://kgon.tistory.com/33
- https://velog.io/@jisoo1170/Oracle-MySQL-PostgreSQL-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%80
