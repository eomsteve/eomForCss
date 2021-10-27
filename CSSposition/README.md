# CSS position

CSS 포지션 속서은 문서상에  요소를 배치하는 방법을 지정한다. top, right, bottom, left 속성이 요소를 배치할 최종 위치를 결정한다.

### static

요소를 일반적인 문서 흐름에 따라 배치한다. 기본값(모든 HTML 요소의 position 속성값은 static이다.)

요소를 위에서부터 아래쪽으로 순서대로 배열시켜주는 속성이다.

### relative

요소를 일반적인 문서 흐름에 따라 배치하고, **자기 자신** 을 기준으로 `top`,`right`,`bottom`,`left` 의 값에 따라 오프셋을 적용한다. 오프셋은 다른 요소에 영향을 주지 않는다.  

### absolute

고정위치가 뷰 포트를 기준으로 위치를 결정하는것과 비슷하게 동작한다. 단지 뷰포트를 기준으로 위치를 결정하는것이 아닌 설정된 조상 요소를 기준으로 위치를 설정하게 된다. 조상 요소가 없다면 문서의 body 요소를 기준위치를 설정하게 된다.

### fixed

뷰 포를 기주으로 위치를 설정하는 방식이다. 즉 웹페이지가 스크롤 되어도 고정 위치로 지정된 요소는 항상 같은 곳에 위치하게 된다.

### sticky

문서 흐름에따라 배치하고 테이블관련 요소를 포함해 가장 가까운 스크롤 되는 조상과 표 관련된 요소를 포함한 블록을 기준으로 오프셋을 적용한다.

sticky 박스는 top, right, bottom, left 속성이 필수이다.

#### 각 속성의 상대적 위치 설정하는 방법

relative : 해당 요소가 정적 위치 지정방식일 때의 위치에 상대적으로 위치한다.

fixed :  뷰포트에 상대적으로 위치한다.

absolute : 위치가 설정된 바로 상위의 조상 요소에 상대적으로 움직인다. **position: static 속성을 가지고 있지않은 부모를 기준으로 움직인다.** 

-----

references

https://keichee.tistory.com/277

https://developer.mozilla.org/ko/docs/Web/CSS/position

http://tcpschool.com/css/css_position_position

실습 : https://www.nhis.or.kr/_custom/nhis/_common/board/index/719.do?mode=view&articleNo=209026&title=%EA%B0%80%EC%9E%85%EC%9E%90%EB%AA%85%EB%B6%80%28%EC%82%AC%EC%97%85%EC%9E%A5%29%2C+%EA%B0%80%EC%9E%85%EB%82%B4%EC%97%AD%ED%99%95%EC%9D%B8%EC%84%9C%28%EC%82%AC%EC%97%85%EC%9E%A5%2F%EA%B0%9C%EC%9D%B8%29+%EB%B0%9C%EA%B8%89%EC%9D%84+%EC%9B%90%ED%95%98%EC%8B%9C%EB%8A%94+%EA%B2%BD%EC%9A%B0