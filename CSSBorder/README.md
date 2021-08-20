# CSS : Border

`border` 속성은 테두리를 설정하는 요소이다. `border-width` , `border-style`, `border-color` 의 값을 설정한다.

스타일을 사용하지 않으면 기본값은 `none` 으로 테두리가 보이지 않는다.

#### border style

* dashed : 테두리를 긴 점선으로 설정한다.
* dotted : 테두리를 점선으로 설정한다.
* double : 테두리를 2중 실선으로 설정한다.
* groove : 테두리를 3차원인 입체적인 선으로 설정, border-color 속성값에 영향을 받는다.
* hidden : 테두리가 존재하나 표현되지 않는다.
* none : 테두리를 없앤다
* inset : 테두리를 3차원 내지로 끼운 선으로 설정한다.
* outset : 테두리를 3차원인 외지로 끼운선으로 설정한다.
* ridge : 테두리를 3차원 능선효과가 있는 선으로 설정한다.
* solid : 테두리를 실선으로 설정한다.

#### border width

* medium
* thick
* thin
* length : (number)

#### border radius

테두리를 원형으로 깎을 수 있다. `length` 또는`percentage` 값으로 설정이 가능하다.

* 픽셀과 퍼센트 값의 차이점 : % 단위 사용시 사각형의 가로 길이또한 비율만큼의 크기가 둥글게 외곽선이 표현된다.
* 일반적인 픽셀 사용시 둥글게 표현되는 크기가 가로와 세로 동일한 값으로 적용된다. 

### 테두리 개별 설정

CSS를 사용하면 테두리의 위쪽, 오른쪽, 아래쪽, 왼쪽 부분에 대하여 개별적으로 스타일을 적용할 수있다. `top` `right` `bottom` `left`  순으로 설정한다. 

![](http://tcpschool.com/lectures/img_css_boxmodel_border.png)

border-style: dotted dashed solid double;

= 

​	border-style-top: dotted;

​	border-style-right: dashed;

​	border-style-bottom: solid;

​	border-style-left: double;

-----

references 

https://developer.mozilla.org/ko/docs/Web/CSS/border

https://www.codingfactory.net/10620

http://tcpschool.com/css/css_boxmodel_borders

> DoD : 정사각형의 붉은 윤곽선을 가진 div하나, 동그란 파란 윤곽선을 가진 div하나 삼각형 모양의 div 하나를 담은 html문서

