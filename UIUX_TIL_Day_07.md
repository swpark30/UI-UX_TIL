# UIUX_TIL_Day_07



- 목차
  - 사용자 정의 객체
    - 객체 생성 방법
      - 리터럴 이용
      - 생성자 함수 이용
      - new Object() 이용
      - class 정의하고 객체 생성
    - JSON 처리 방법
  - jQuery
    - 특징
    - 사용목적
    - jQuery 치환
    - jQuery 선택자(selector)
    - jQuery 변수
    - jQuery 이벤트
    - jQuery DOM 요소 조작



### 사용자 정의 객체

- 사용자가 직접 필요한 객체 생성

- 객체 멤버 

  - 속성 : 데이터
  - 메소드 : 기능(작업)

  

- 객체 생성 방법

  - 리터럴 이용

    ```javascript
    var 객체 = { // 객체 생성
        //멤버 추가
        속성(프로퍼티) : 속성값,
        //멤버 메소드
        메소드명 : function(){
            수행코드;
        }
    };
    
    객체.메소드명(); // 객체의 멤버 메소드 사용
    ```

    

  - 생성자 함수 이용

    - 함수 선언과 같은 방식으로 function 키워드 사용하여 선언 

    - 함수를 클래스처럼 사용

      - function 함수명(){...} : 생성자 기능

    - this.프로퍼티 (속성)

    - new 연산자 사용해서 객체 생성

      ```javascript
      function 함수명() {
          // 멤버 추가
          this.프로퍼티1 =값1;
          this.프로퍼티2 =값2;
          
          this.메서드 = function(){  
          };
      }
      
      // 객체 생성
      var 객체(인스턴스) = new 함수명();
      객체.메소드(); // 객체의 멤버 메소드 사용
      객체.프로퍼티1;
      ```

      

  - new Object() 이용(ES5에 추가)

    ```javascript
    var person = new Object(); // 빈 객체 생성(new 생략 가능)
    
    //프로퍼티 추가
    객체.프로퍼티(속성) = 값;
    
    //멤버 메소드 추가
    객체.함수명 = function(){
        수행 코드
    }
    
    개체.메소드(); // 객체의 멤버 메소드 사용(호출)
    ```

    

  - class 정의하고 객체 생성(ES6에 추가)

    - class 키워드 사용
    - 생성자 / getters/ setters 가능
    - 호이스팅 불가

​	

#### JSON 처리 방법

- JSON(JavaScript Object Notation)

  - 자바스크립트 객체 표기법
  - key와 value 값이 쌍으로 구성된 형태의 객체 표기법
  - 클라이언트와 서버 사이에서 데이터 교환 목적으로 사용
  - 웹 서버에서 수신하는 데이터는 문자열인데, 문자열 데이터를 JSON 파싱 함수를
    사용해서 파싱하면 자바스크립트 객체로 변환 가능 
  - 최근의 브라우저들은 전부 내장 객체로 JSON 변환 기능 지원

  

- 데이터 형식

  ```javascript
  {key:value} : {"name":"홍길동"}
  ```

  

- 메소드

  - JSON.stringify()
    - 자바스크립트 객체를 JSON data로 변환
  - JSON.parse()
    - JSON data를 자바스크립트 객체로 변환





## jQuery



- 2006년 존 레식(John Resig)이 디자인 자바스크립트 라이브러리
- 라이브러리
  - 자바스크립트를 이용해 만든 다양한 함수들의 집합
- 무료 사용 가능한 오픈 소스 라이브러리
- 모든 웹 브라우저에서 동작



### 특징

- 용량이 약 100KB로 가벼움
- 동적으로 HTML이나 CSS 컨트롤 능력 탁월
- 짧고 간결하게 코딩 가능
- 웹 표준과 타 브라우저 호환성 뛰어남 (크로스-브라우저 지원)
- 편리한 Ajax 호출 방법
- 메소드 체인 방식 (여러 메소드를 연결하여 사용)으로 효율적인 코딩 가능
- 간결하고 효과적인 코드수정 가능
- 다양한 플러그인 제공



### 사용 목적

- 쉬운 DOM 처리
- 쉽고 일관된 이벤트 연결 구현
- 쉬운 시각적 효과 구현
- Ajax 기능 쉽게 구현



개발 환경

1. jQuery 파일 다운로드 방식

   - 웹 애플리케이션에 HTML,CSS,JavaScript 파일들과 같이 jQuery 파일 있어야 함

2. CDN 이용하는 방식

   - Content Delivery Network

   - 사용자가 요청한 콘텐츠를 사용자와 가장 가까운 곳에 위치한 캐시 서버에서 
     전달해 주는 방식

     

### 코드 형태

- 객체 구조로 객체.메소드 형태

- 객체 선택

  - $("선택자").메소드;

- 사용자가 생성한 객체 사용

  ```javascript
  var obj =  $("선택자").메소드;
  obj.메소드;
  ```

- 메소드 체이닝

  - 여러 개의 메소드를 연결해서 사용하는 것

    ```javascript
    객체.메소드1.메소드2. ......
    ```



### jQuery 치환

- jQuery의 모든 함수 및 객체는 jQuery에서 제공되는 것이라는 점을 나타내기 위해 코드
  앞에 jQuery 키워드 사용

  ```javascript
  jQuery(document).ready(function(){...});
  
  // 쉽게 하기 위해 $문자로 치환해서 사용
  $(document).ready(function(){...});
  ```

  

$(document).ready(함수) 명령어

- 화면에 페이지가 로딩되어 실행

- HTML 문서가 화면에 보여진 후에 자동으로 포함된 함수 실행

- 자바스크립트의 window.onload = function(){};에 해당

  

$(document).ready()와 window.onload = function() 차이점

- 같은점
  - 콜백 함수가 호출되는 시점에서 DOM 요소에 접근 가능
- 차이점
  - $(document).ready()
    - DOM 요소가 로드 되었을 때 이벤트 발생하면서 호출
      (외부 리소스, 이미지 또는 사운드 등이 로드 되기 전)
  - window.onload = function() 
    - DOM 요소 뿐 아니라 외부 리소스, 이미지, 사운드 등 모든 콘텐츠의
      로드가 끝나는 시점에서 이벤트가 발생하면서 호출



### jQuery 선택자(selector)

- jQuery 코드는 선택자와 메소드의 조합으로 구성되는 경우가 많음

- HTML 태그를 쉽게 선택하기 위해 선택자 사용

  

- 선택자 구조

  - $("선택자").메소드(매개변수, 함수 등);
  - $("span").hide();
    - 큰 따옴표, 작은 따옴표 다 사용 가능

  

- #### 선택자 종류

  - 직접 선택자

    - 전체, 태그, 아이디, 클래스

    

  - 인접 관계 선택자

    - 부모, 조상, 자식, 자손, 형제

    

  - 필터 선택자

    - 태그의 상태나 순서 등으로 선택

      ```javascript
      $("태그명:순서필터")
      $("tr:odd") : 홀수 행인 경우
      
      $("태그명:상태필터")
      $("input:checked") : 체크 상태인 경우
      ```

    

  - 속성 선택자

    - 문서에 삽입된 HTML 태그의 지정된 속성 값에 따라 선택자로 정의



### jQuery 변수

- 변수명 앞에 $ 붙임

  ```javascript
  var $box1 = $("#box1");
  // $box1의 타입은 object로 jQuery 메소드 사용 가능
  
  $box1.css('color', 'red');
  var $divLen = $('div').length; // div 태그 개수 저장
  // $divLen의 타입은 Number
  
  // 이 경우 일반적으로 $ 붙이지 않음 (자바스크립트 변수)
  var divLen = $('div').length;
  ```

  

### jQuery 이벤트

- 기존의 자바스크립트에서 사용했던 이벤트 대부분 사용

- jQuery를 이용하여 이벤트를 처리하면 훨씬 간단하고 쉽게 이벤트 처리 가능

  

- 사용 기본 구조

  ```javascript
  $('#btn').click(function(){...});
  ```

  - 이벤트 대상 : $('#btn')
  - 이벤트 등록 메소드 (이벤트 유형) : click()
  - 이벤트 핸들러 (이벤트 처리 함수) : function(){...}

  

- 등록 메소드 유형

  - 단독 이벤트 등록 메소드

    ```javascript
    $('#btn').click(function(){...});
    // 주의 - 동적 연결 지원 안됨
    // 동적으로 생성된 객체에 이벤트 적용 안됨
    ```

    

  - 그룹 이벤트 등록 메소드(여러 이벤트 적용)

    ```javascript
    $('#btn').on('mouseover focus', function(){...});
    // 동적으로 생성된 요소에 적용 가능
    ```

    

- 연결 방식

  - 정적 연결

    - 현재 HTML 화면에 있는 태그에만 이벤트 연결
    - jQuery를 통해 새로 삽입되는 태그에는 이벤트 연결 안됨

    

  - 동적 연결

    - 현재 HTML 화면에 표시된 요소와 앞으로 생성될 요소에 전부 이벤트 연결 가능

  

- #### 이벤트 종류

  - 윈도우 이벤트

    - ready
    - resize
    - scroll
    - load
    - unload

    

  - 입력 양식 이벤트

    - submit

      - input 입력란에서 엔터키 쳤을 때 문제

        - input 태그의 입력란에서 엔터키를 치면 무조건 submit 이벤트가
          발생하면서 submit() 호출하고 서버로 전송되는 문제 발생

        - 엔터키 쳤을 때 submit 되지 않도록 문서 전체에 이벤트 처리 
          [Enter]키의 아스키 코드 값 : 13

          ```javascript
          if(e.keyCode == 13) return false;
          // 문서 전체에 이벤트 처리
          ```

          

    - reset

    - change

    - focus

    - blur

    

  - 마우스 이벤트

    

  - 동적 연결 이벤트

    - 동적으로 생성된 버튼에 이벤트 연결

    

  - 키보드 이벤트

    - 종류
      - keyup
      - keydown
      - keypress

    

### jQuery DOM 요소 조작

- 동적으로 DOM 요소 조작
- jQuery를 이용하면 쉽고 간단하게 조작 가능
- DOM 요소 삽입/ 삭제 / 속성 추가 및 삭제



- DOM 요소 관련 주요 메소드

  - text() 와 html()메소드
    - 자바스크립트의 innerHTML 속성과 유사
    - 선택한 DOM 요소에 글자(텍스트)를 설정하거나 반환
    - html()
      - HTML 태그 인식(태그 효과 적용)
    - text()
      - HTML 태그 인식하지 못하고 글자로 인식

  

- DOM 요소의 속성 추가 및 삭제

  - attr(속성명, 값) : 속성 추가
  - removeAttr(속성명) : 속성 제거 
  - attr() : 속성 설정, 조회 
  - prop() : 활성화, 체크, 선택여부 등 동적 적용







