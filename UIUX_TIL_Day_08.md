# UIUX_TIL_Day_08



- 목차
  - jQuery
    - DOM 요소에 CSS 효과 동적 적용
    - jQuery 효과




## jQuery



### DOM 요소에 CSS 효과 동적 적용

- CSS 클래스 선택자에 적용된 여러 효과를 동적으로 추가하거나 삭제

- addClass("클래스명") : CSS 효과 적용

- removeClass("클래스명") : 적용된 CSS 효과 해제

- toggleClass("클래스명")

  - addClass와 removeClass()를 번갈아 가면서 실행하는 결과

  ```javascript
  <style>
      .h1Css {...}
  </style>                         
  ```
  
  

### jQuery 효과

- 시각적 효과

  - 공통 인수 

    - duration : 효과 진행 속도 (slow / nomal / fast)
    - callback(function()) : 효과 완료 후 수행할 함수
    - easing
      - 전체 애니메이션의 적용 시간 비율을 원하는 진행 비율로 매핑
      - swing : 사인 곡선 (느리게 시작해서 빠르게 진행되다가 나중에 다시 느려지는 효과)
      - linear : 선형 (일정한 속도로 진행)

    

  - Basic 효과
  
    - hide() : 요소 숨기기
    - show() : 요소 표시
    - toggle() : 요소를 숨기거나 표시

    
  
  - sliding 효과
  
    - slideDown() : 요소를 슬라이딩 효과로 나타나게 함
    - slideUp() : 요소를 슬라이딩 효과로 숨김
    - slideToggle() : 슬라이딩 해서 숨겼다가 보였다가 교대로 실행
    - 주의
      - 슬라이딩 효과는 div 박스에 적용
      - 이미지에 슬라이딩 효과를 주면 전체적으로 축소/ 확대되면서 
        사라졌다가 보여짐
  
    
  
  - Fading 효과
  
    - fadeIn() : 요소를 선명하게 만들면서 나타남
    - fadeOut() : 요소를 흐리게 하면서 숨김(영역도 사라짐)
    - fadeToggle() : fadeIn() / fadeOut() 교대로 실행
    - fadeTo() 
      - 요소의 불투명도 조정
      - 투명도 0으로 안 보여도 영역은 그대로 남아 있음

    

  - Animate 효과
  
    - animate(속성)
  
      - 사용자 CSS 효과를 지정하여 애니메이션 수행

    - 형식1

      ```javascript
      $('대상').animate(
      	{속성(CSS)},
           duration(효과 진행 속도),
           'easing'(진행 효과),
      );
      ```
  
    - 형식2
    
      ```javascript
      $('대상').animate(
      	{속성(CSS)},
           duration(효과 진행 속도),
           'easing'(진행 효과),
           function(){(효과 완료 후 수행할 함수)
          	수행 내용
      	}
      );
      ```
  
      
    
    - 애니메이션 정지
    
      ```javascript
      $(선택자).stop(); // false 입력한 것으로 간주
      $(선택자).stop(true);  // clearQueue 수행
      $(선택자).stop(true, true); // clearQueue, goToEnd 수행
    
    - clearQueue
      - 대기열에 있는 함수 모두 제거
      - 예약된 애니메이션 초기화
      - clearQueue() 메소드 실행 효과
      
      
      
    - goToEnd
      
      - 제자리에서 멈추는 것이 아니라 지정한 최종 형태에서 멈춤
        (애니메이션 진행 중간에 멈추는 것이 아니라 마지막까지 수행되고 멈춤)
    
    

