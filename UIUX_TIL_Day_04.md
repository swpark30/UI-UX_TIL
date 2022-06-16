# UIUX_TIL_Day_04



- 목차
  - 자바스크립트
    - 데이터를 출력하는 기본 방법
    - 데이터 입력
    - 변수 선언 (명시적 선언)
    - var vs let vs const
    - 호이스팅 (Hoisting)
    - 자바스크립트에서 사용되는 데이터 타입
    - 제어문 
    - 배열
    - 자바스크립트 함수



## 자바스크립트



### 데이터를 출력하는 기본 방법

- window.alert(내용)
  - 출력내용을 알림창(경고창)으로 출력
  - window 객체 생략 가능
- console.log(내용) : 개발자 도구의 Console 창에 출력
- document.write(내용)
  - 화면(문서)에 내용 출력
- DOM(문서 객체 모델) 사용 (태그에 출력)



자바스크립트 코드 입력시 주의점

- 대소문자 구별
- 문장 끝에 세미콜론 사용
- 문자열에서 따옴표 겹침 오류 주의
- 괄호 짝이 맞아야 함



### 데이터 입력

- confirm() : 함수로 입력 받기

  - 자바스크립트 내장 함수
  - [확인] / [취소] 버튼이 있는 대화상자 출력하고 
    - [확인] 버튼 누르면 true 반환
    - [취소] 버튼 누르면 false 반환

  

- prompt() : 함수로 입력 받기 (연습용)

  - 자바스크립트 내장 함수
  - 사용자로부터 입력 받은 값을 반환
  - 매개변수
    - prompt("출력 메세지");
    - prompt("출력 메세지", "기본값");

  

- DOM 사용

- input 태그와 value 속성 사용



주석문

- Java와 동일



변수

- 프로그램 실행 중에 값을 저장하기 위한 메모리 내의 임시 기억장소



### 자바스크립트에서 식별자(변수명, 함수명 등) 명명 규칙

- 시작은 반드시 영문자나 _ 사용,숫자 사용할 수 없음

- 대소문자 구별
- 키워드 사용 할 수 없음
- 특수문자나 공백은 사용할 수 없음
- 한글 사용가능 (영문 사용 권장)
- 의미 있는 단어 사용 (예: name, address, age)



### 변수 선언 (명시적 선언)

- var
- let
- const
- ES6 이후 var 보완하기 위해 추가된 변수 선언 방식
  - let과 const

- 변수를 필요한 곳에 사용하면 자동으로 생성되기 때문에 반드시 선언하지 않아도 됨
- 변수의 데이터 타입은 실행 시 결정 (동적 타이핑)
- 명시적으로 선언할 경우에 예약어 var(let, const) 사용
  - 명시적 선언 권장



#### 정적 타이핑 언어 vs 동적 타이핑 언어

- 타입(type) : 자료형 (데이터의 타입)
- 정적 타이핑 언어
  - 변수의 데이터 타입을 컴파일 시에 결정
  - C, C++, Java등
  - 선언한 변수의 데이터 타입에 따라 값 저장
  - int a = 10;
- 동적 타이핑 언어
  - 변수의 데이터 타입을 실행 시 결정
  - 데이터 타입 지정하지 않고 변수에 값 저장
  - var name = "홍길동";
  - num = 100;
  - JavaScript, Python 등



#### 변수의 유형

- 전역 변수(멤버 변수)

  1. 전역변수 범위 (script태그 바로 아래)에 명시적으로 선언하거나
  2. 명시적으로 선언하지 않고 사용하는 변수
     - var가 붙든 안붙든 다 전역변수
  3. 자바스크립트 코드 내 모든 곳에서 사용가능

  

- 지역변수

  - 함수 내에서 var 붙여서 선언된 변수
  - 함수 내에서만 사용가능
  - 함수 내에서 var 붙이지 않고 사용하는 변수는 전역변수로 간주



### var vs let vs const

- var와 let의 차이점1

  - var는 동일한 변수명으로 여러 개 선언해도 오류 없음
  - let은 이미 선언된 변수명으로 선언 불가

  

- var와 let의 차이점2 : scope (범위)

  - var : function 단위의 scope
  - let : block ({}) 단위의 scope

  

- let과 const의 차이

  - let : 재할당 가능 (값 변경 가능)
  - const : 재할당 불가 (값 변경 불가)



#### 호이스팅 (Hoisting)

- 변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것

- 선언은 뒤에 했는데 선언문 전에서 변수 사용하는 것

- var로 선언된 변수는 가능

- let으로 선언된 변수는 불가

  ```javascript
  console.log(name);
  
  var name ="홍길동"; 선언과 초기화
  ```

  

### 연산자

- 자바와 동일



#### 자바스크립트에서 사용되는 데이터 타입

- 숫자 : 정수형, 실수형
- 문자 : 'a'
- 문자열 : "string" '작은 따옴표도 가능'
- NaN
  - Not a Number (숫자가 아닌데 숫자로 사용할 경우)
- 논리값 : true / false
- undefined 와 null
  - null : '참조 객체 없음'의 의미 (값이 없을 때)
  - undefined : 값의 유형을 알 수 없음



#### 데이터 형변환

- parseInt() : 정수값으로 형변환
- parseFloat() : 실수값으로 형변환
- String() / toString() : 문자열로 형변환



### 제어문 

- 자바랑 동일

- switch 문에서 수식으로는 값의 결과가 정수, 실수, 문자열, 객체 값이어야 한다.
  - 자바에선 정수랑 문자 값만 되는 거랑 다르다. 
  
- for in 문
  - 배열이나 객체를 쉽게 탐색
  
    ```javascript
    for(var i in 배열){
        num = arr[i];
    }
    ```
  
    

### 배열

- 동일한 이름을 갖는 원소들의 연속적 저장 영역

- 배열의 원소는 메모리 내에서 순서대로 저장

- 각 배열의 원소는 인덱스([0]부터 시작)로 구별

  ```javascript
  var num = new Array(3);
  ```

- 배열의 크기 (원소의 개수) : length 속성
  - num.length
  
- 자바스크립트의 배열은 각 원소에 다른 유형의 데이터 저장 가능 

- 배열 사용
  - 배열 원소에 값 저장
  
    ```javascript
    a[2] = 10; //3번째 원소에 10 저장
    ```
  
  - 배열 원소에 들어 있는 값 출력
  
    ```javascript
    - var x = arr[0]; //변수에 배열 첫 번째 원소값 저장
    - document.write(a[1]);//2번째 원소의 값 출력
    ```
  
  - !!!주의
  
    - 배열의 전체 원소에 값을 저장하거나 출력하기 위해서는 반복문 사용
    - 배열은 크기가 정해져 있기 때문에 반복 횟수를 정할 수 있으므로 for문 사용
    - 반복문 시작은 반드시 0부터(첨자가 [0]부터)



#### 자바스크립트 함수

- (자동 호출되는 함수)
- 선언적 함수 (일반 함수 : function() {  })
- 익명 함수 
- 콜백 함수
- 화살표 함수
- 디폴트 매개변수




