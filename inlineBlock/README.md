# In line And Block

CSS에서 `display` 속성은 웹페이지 상에서 요소들이 어떻게 보여지고 다른 엘리먼트와 어떻게 상호 배치되는지를 결정한다. 여러가지`display` 속성값중에서 가장 기본이되는 `inline` 과 `block`  그리고 `inline-block`에 대해 알아본다.

### block-level Elements

블록 수준 요소는 항상 새 줄에서 시작하고 사용 가능한 전체 너비를 차지한다. 가능한 한 왼쪽과 오른쪽으로 늘어난다.(width=100%)

block 은 height와 width값을 지정할 수 있다.

block은 margin과 padding을 지정할 수 있다.

* div
* h1~h6
* p
* form
* header
* footer
* section
* address
* article
* aside
* hr
* canvas
* table
* ul
* ol

### inline Elements

인라인 요소는 새 줄에서 시작하지 않고 필요한 만큼만 너비를 차지한다.

width와 height를 명시 할 수 없다.

margin은 위아래엔 적용 되지 않는다.

padding은 좌우는 공간과 시각적인 부분이 모두 적용 되지만 위아래는 시각적으로는 추가되지만 공간을 차지 하지는 않는다.

* span
* a
* img
* button

### inline-block

인라인과 블록의 특징을 모두 가진요소이다. 기본적으로 인라인 요소처럼 줄바꿈없이 한줄에 다른 요소와 나란히 배치된다. 

- 줄바꿈이 이루어지지 않는다.
- block처럼 width와 height를 지정 할 수 있다.
- 만약 width와 height를 지정하지 않을 경우, inline과 같이 컨텐츠만큼 영역이 잡힌다.

-----

https://www.w3schools.com/css/css_display_visibility.asp

https://seungwoohong.tistory.com/23

