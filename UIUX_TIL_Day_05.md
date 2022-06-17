# UIUX_TIL_Day_05



- 목차
  - 자바스크립트
    - 자바스크립트 함수
      - 일반 함수(function)
      - 익명 함수(Anonymous Function)
      - 콜백 함수(Callback Function)
      - 화살표 함수(Arrow Function)
      - 디폴트 매개변수(Default Parameter)
    - 자바스크립트 객체(Object)
      - 내장 객체(Built in Object)





## 자바스크립트





### 자바스크립트 함수



- #### 일반 함수(function)

  - 특정 기능을 수행하고 결과를 돌려주는 독립적인 코드 집합

  - 독립적인 모듈 {}

  - 메소드, 모듈, 기능, 프로시저 등으로 불림

  - 함수를 사용하기 위해서는 반드시 호출해야 함

    

  - 함수 선언 형식

    ```javascript
    function 함수명() { 
        // 함수 body : 수행 문장
    }
    
    // 스스로 동작하는 함수
    (function(){....})();
    // 함수 호출 없이도 자동 실행
    
    // 함수 호출
    함수명();
    
    //다른 함수 내에서 함수 호출 가능
    function show(){
        input();
    }
    ```

  

  - 함수의 반환 값

    - 함수 실행이 끝난 후 호출한 곳으로 돌려주는 결과값
    - 함수 내에서 return 문 사용

    ```javascript
    function sum(){
        return n1 + n2;
    }
    document.write("합계 : " + sum()); // 이 자리로 리턴값 반환
    
    변수.toFixed(자리수); // 소수점 자리수까지만 쓰는 방법
    변수..toLocaleString(); // 천 단위로 끊어서 출력하는 방법
    ```

    

  - 함수의 매개변수

    - 함수 호출 시 전달된 값을 받기 위해 사용되는 변수

      ```javascript
      function sum(x,y){
          return x + y;
      }
      document.write("합계 : " + sum(10,20));
      ```

    

  - 함수 호이스팅 

    - 함수 선언보다 먼저 함수 호출해서 실행되는 기능

    - function 키워드 사용해서 생성한 함수는 호이스팅 가능

      ```javascript
      show(); // 먼저 호출 : 함수 호이스팅 가능
      
      function show() { // 나중에 함수 선언(정의)
          ......
      }
      ```

      

- #### 익명 함수(Anonymous Function)

  - 함수명 대신 변수명에 함수 코드를 저장하는 구현 방식

  - 익명함수의 호이스팅 불가

    ```javascript
    var 변수명 = function(매개변수){};
    ```

  

- #### 콜백 함수(Callback Function)

  - 매개변수로 함수를 전달받아서 함수의 내부에서 실행하는 함수

  - 인자로 넘겨지는 함수를 콜백 함수라고 부름

  - 콜백 함수로는 주로 이름이 없는 익명 함수 사용

    ```javascript
    // 익명함수를 콜백함수로 전달
    			
    // 익명함수
    var callback = function(){
        alert("익명함수 입니다");
    };
    
    // 함수로 매개변수로 받을 함수 : 콜백 함수 받아서 사용
    function show(callback){ // a로 받아도 됨 : 호출할 때 a()로 하면 됨
        // 매개변수로 받은 콜백 함수 사용 (호출)
        callback();
    }
    
    show(callback); // show() 함수 호출하면서 함수를 인자로 전달 (전달되는 함수 : 콜백 함수)
    ```

    

    

  - 일반적인 콜백 함수 의미

    - 등록해 놓은 이벤트 또는 특정 시점이 되었을 때 시스템에서 호출하는 함수

    

  - 사용하는 이유

    - 자바스크립트에서 비동기 처리 방식의 문제점을 해결하기 위해 사용
    - 자바스크립트는 단일 스레드
      - 하나의 작업이 끝나고 다른 작업을 수행
      - 동시에 여러 개의 작업을 수행하지 않음
    - 콜백 함수를 사용해서 다른 작업이 끝나기 전에 비동기적으로 작업을
      수행하는 것이 가능

    

  - 주의점

    - 콜백 지옥 발생
      - 콜백 함수를 함수로 전달하는 과정이 반복적으로 이루어져 계속 들여쓰기 
        형식으로 콜백 함수를 하다보면 감당하기 어려울 정도로 수준이 깊어짐
    - 콜백 지옥 해결 방법
      - Promise : ES6 도입
      - async-await : ES8 추가
        - callback 지옥 문제를 해결할 뿐 아니라 단순하고 직관적인
          코드 작성이 가능

    

  - 콜백 함수에서 지역변수를 매개변수로 전달

    - 함수 내의 지역변수를 콜백 함수 호출하면 전달 가능

      ```javascript
      function call(callback) {
      	var localVar = 1;
          callback(localVar);
      }
      ```

  

- #### 화살표 함수(Arrow Function)

  - function 키워드 대신 화살표(=>)를 사용하여 간결한 방법으로 함수를 선언하는 방법
    (자바의 람다식과 비슷)

    ```javascript
    () => { ... } // 매개변수가 없는 경우
    x => { ... } // 매개변수 한 개인 경우. () 괄호 생략 가능
    (x,y) => { ... } // 매개변수가 여러 개인 경우 괄호 생략 불가
    x => {return x*x} // 리턴값 있는 경우
    x => x*x // 1줄인 경우 return 생략 가능
    ```

    

- #### 디폴트 매개변수(Default Parameter)

  - 매개변수를 디폴트로 설정해 놓으면 전달되는 값이 없을 경우 디폴트 매개값으로 적용

  - 순서 주의

    - 디폴트 매개변수와 일반 매개변수를 섞어서 사용할 경우

    - 디폴트 매개변수를 맨 뒤에 위치시킴

      ```javascript
      // 디폴트 매개변수가 있는 함수
      function rect(width=10, height=20){
          document.write("width : " + width);
          document.write("height : " + height + "<br>");
          return width * height;
      }
      
      console.log(rect()); // 값을 전달하지 않으면 디폴트 매개변수 width, height로 사용
      console.log(rect(30)); // 값을 1개 전달하면 첫 번째 매개변수가 받고, 두번째는 디폴트 매개변수 사용
      console.log(rect(100, 200)); // 값을 2개 다 전달하면 전달받은 값으로 사용 (디폴트 매개변수 사용 안 함)
      ```

      





### 자바스크립트 객체(Object)



- #### 내장 객체(Built in Object)

  - 미리 정의되어 있는 객체

  - 선언 과정을 통해 객체 변수를 정의해서 사용

  - 특별한 경우에는 사용자 정의 객체를 정의하여 사용

  - 대부분의 경우에는 내장 객체 사용

    

  - 대표적인 내장 객체

    - Date 객체 

      - 날짜와 시간을 처리하기 위한 객체

      - 웹 페이지에 오늘 날짜와 시간 및 요일 등 표시

        ```javascript
        var today = new Date();
        var month = today.getMonth();
        
        today.getMonth();
        ```

      - 메소드

        - getYear(), getMonth(), getDate(), getDay(), getHours(), getMinutes()

        - getSeconds(), getTime()

        - 설정하려면 setXXX(), get과 동일

          

    - Array 객체

      - 배열을 만들기 위한 객체

        ```javascript
        var arr = new Array(3);
        
        arr.push(“홍길동”); // 객체.메소드()
        arr.sort();
        ```

      - 메소드

        - unshift(데이터), shift(), push(데이터), pop(), reverse(), sort()

        - slice(start, end), splice(위치, 개수, 데이터)

          

    - String  객체

      - 문자열을 다루기 위한 객체

        ``` javascript
        var name = new String();
        name.fontsize(5);
        ```

        

      - new를 이용해서 객체를 생성하지 않고 상수 형태("문자열")로 문자열을 만들어도 객체의 특징 모두 사용

        ```javascript
        var name = “홍길동”;
        name.fontsize(5);
        // 객체로 자동 변환 : 일시적
        ```

      - 메소드

        - charAt(), indexOf(), lastIndexOf(), substring(), slice(), substr(), 
        - toUpperCase(), toLowerCase(), concat(), split()

        

      - charAt(인덱스)

        - 인덱스로 지정된 위치의 문자 반환
        - str.charAt(3) : 문자열 str에서 4번째 문자 반환
        - 인덱스는 0부터 시작

        

      - substring(start, end)

        - 문자열 일부분 추출
        - 인덱스 start ~ end-1 까지의 문자열

        

      - indexOf("문자")

        - 문자열에서 지정된 문자의 위치를 인덱스 값으로 반환

        - 검색할 때 왼쪽부터 찾아서 처음 발견한 문자의 위치를 알려주는 것

        - 찾고자 하는 문자가 문자열에 없으면 -1 반환

          ```javascript
          emai.indexOf(“@”); 
          ```

          

      - split("구분자")

        - 구분자로 문자열 분리

          ```javascript
          str = "1998-12-25"
          var birth = str.split("-");
          
          // birth[0]에 1998이 저장
          // birth[1]에 12가 저장
          // birth[2]에 25가 저장
          ```

          

    - Math 

      - 상수 값은 속성으로 수학은 메소드로 제공

      - Math 객체는 속성이나 메소드를 접근하기 위해 따로 객체 변수 선언 하지 않음

      - 형식

        ```javascript
        Math.속성 // Math.PI : 원주율
        Math.메소드() // Math.abs() : 절대값
        ```

      - 메소드

        - sin(x), cos(x), tan(x), abs(x), exp(x), log(x), random(x), pow(x,y)
        - sqrt(x), round(x), floor(x), ceil(x), max(x,y), min(x,y)

        

      - random()

        ```javascript
        1 ~ 10 사이의 수 중에서 랜덤 숫자 생성
        
        var num = 1 + Math.floor(Math.random() * 10);
        // 0.01223454  ~ 0.999999999 : 0과 1 사이의 실수
        // 곱하기 10 : 0.xxx, 1.xxx
        // floor() : 소수점 이하 버리고
        // 1부터 시작하도록 베이스를 + 1
        ```

        

    - Screen : 화면의 해상도, 색상, 크기에 관한 정보를 제공하는 객체

      

