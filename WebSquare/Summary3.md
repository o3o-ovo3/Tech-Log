# WebSquare5 배워보기 - 개발자 과정

✍️ *Written by Yunju Jang*

 🚩*2021.09.02*

## 4. 데이터 통신하기

#### 4-1) 데이터 통신 방법

- <b>Submission에서 통신을 만들어 사용</b>

  - ID : 통신의 이름
  - Reference : 화면에서 초기값을 Servlet으로 던져주기 위한 DataCollection
  - Target : Servlet에서 화면으로 값을 던져주기 위한 DataCollection
    - 위 두 DataCollection은 사전에 만들어져있어야 하며, 이와 엮어준다.
  - URL Action : 결과를 처리하는 경로 (Servlet 정보)
  - Process Message : 처리중이라는 문구 등을 작성한다. Progress Bar도 제공한다.
  - <mark>submit</mark> : 처리 Servlet 구동 직전 (통신 직전)에 마지막으로 화면에서 수행되는 스크립트 함수 (ex. 초기값 처리, validation 체크 등)
  - <mark>submit-done</mark> : 통신이 끝난 후 가장 먼저 화면에서 수행되는 함수
  - <mark>submit-error</mark> : 통신 중 에러가 발생했을 때 가장 먼저 화면에서 수행되는 함수

  <br/>

- 통신 중에는 버튼을 disable 시킬 수 있다.

  - 충돌을 방지하기 위함

<br/>

<br/>

#### 4-2) 단건의 데이터 받아오기

- 보내는 DataCollection은 DataMap으로 만든다.

  - 단건의 데이터를 보내기 때문에 (ex. 검색할 사원의 사번)

- 받아오는 DataCollection도 DataMap으로 만든다. (ex. 해당 사원 한명에 대한 정보)

  \* 텍스트 파일 등에서 tab으로 구분된 데이터들은 붙여넣기 할 경우 알아서 반영된다.

- Submission 정보에 위의 두 DataCollection과 서블릿 경로를 매핑한다.

<br/>

- <b>보내기</b>
  - 언제 요청할 것인지 기술한다.
    - ex. 조회 버튼을 눌렀을 경우
    - 조회 버튼에 onclick 이벤트를 달고, 해당 부분 script에 executeSubmission 유틸성 메소드를 활용한다.
      - Reference를 이용할 경우 이 부분은 생략이 가능하다.

<br/>

- <b>받아오기</b>

  - 받은 데이터를 컴포넌트에 표현하기 위해 Reference를 건다.

    - DataCollection의 key ID 와 그에 해당하는 각각의 컴포넌트를 매핑한다.

    - DataCollection에서 컴포넌트로 drag&drop을 통해 매핑할 수 있다.

      <img src="../../resources/image.png" width="600px" align="center">

    - 이렇게 Reference를 사용할 경우 script 코딩을 현저히 줄일 수 있다.
