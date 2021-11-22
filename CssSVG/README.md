# SVG : Scalable Vector Graphics

직역하면 확장 가능한 그래픽, SVG는 그래픽을 마크업하기위한 W3C의 특수언어이다. SVG는 `XHTML`과 비슷한 XML언어로 그래픽을 그리는데 사용한다.

#### 장점

* 화면의 크기가 달라져도 깨지지 않는다. svg 이미지는 이미지 그 자체가 아닌 일련의 그리기 명령에 가깝기 때문이다.
* 텍스트 기반 형식이다 : 웹 사이트의 접근성을 향상하고 검색엔진에 의해 색인화가 가능하다.
* 이미지 파일을 http 요청을 할 필요가 없기 때문에 페이지 로드가 더 빠르다.

#### 단점

* 구성요소가 복잡하고 많다면 파일의 크기가 급격하게 커질 수 없다. 
* 사진에는 사용할 수 없다. : 사진을 사용해야 하는 경우 래스터 이미지 형식을 사용해야 한다.

HTML은 헤더, 문단, 표와 같은 요소들을 제공한다. SVG도 마찬가지로 원, 사각형, 간단한 곡선과 복잡한 곡선을 그릴 수 있는 요소들을 제공한다. 간단한 SVG 문서는 루트 요소와 그래픽을 구성하기 위한 몇몇 기본 도형들로 구성된다.

* SVG 태그는 SVG 그래픽을 담기위한 요소이다.

* SVG 태그는 내부에 담을수 있는것은 원, 사각형, 다각형, 라인, path등이 있다.

* SVG 태그는 파일에 모든 요소와 모든속성에 애니메이션을 적용할 수 있다.

  ```css
  <svg width="가로영역" height="세로영역">
  	SVG그래픽
      ...
  </svg>
  ```

  ### SVG 파일 형식

  SVG 파일은 두 가지 형태로 제공된다. 일반 SVG 파일은 SVG 마크업이 포함된 간단한 텍스트 파일이다. 파일 확장자는 ".svg"

  일부 응용프로그램에 사용될 때 매우 큰 크기의 SVG 파일이 있을 수 있기 때문에 SVG 사양에서는 gzip 으로 압축된 파일을 지원한다. 압축 파일의 확장자는 ".svgz"이다. 

##### 그리드

모든 요소에 대해 SVG는 그리드 시스템을 사용한다. 문서의 왼쪽 위 모서리는 (0,0)으로 간주된다.

![](https://developer.mozilla.org/@api/deki/files/78/=Canvas_default_grid.png)

```css
<rect x="0" y="0" width="100" height="100" />
/*왼쪽 상단에서 100px의 정사각형*/
```

##### viewbox

viewbox는 실제 svg 영역중에 보여줄 기준점을 정하는 속성이다. 뷰박스는 가로 세로의 비율을 결정한다.

`viewbox="min-x min-y width height"`   

* min-x : 뷰박스의 x좌표
* min-y ; 뷰박스의 y좌표
* width : 뷰박스의 width
* height : 뷰박스의 height

뷰포트(svg)와 뷰박스가 동일하다면 원래 크기와 동일한 요소가 보인다. 반면 뷰포트가 부박스보다 작다면 축소되어 보이고, 뷰포트가 뷰박스보다 크다면 확대되어 보이게 된다. 

- width 와 height 이 기존보다 작다면 zoom
- 크다면 zoom-out

![](https://media.vlpt.us/images/myungwoo/post/ddcc9e91-1167-4bda-b571-8093fec4a404/270B8D335971CAB204.png)

뷰박스란 기존 하얀 캔버스 위애 내가 어떤 영역을 바라볼지 정한다고 생각하면된다. 위 원이 그려진 캔버스가 전체 svg라고 생각하고 각 색의 박스들이 내가 보고싶은 영역인 뷰박스라고 생각하면 된다.

##### viewbox가 없을때의 모습

![](https://images.velog.io/images/myungwoo/post/32118c70-87cf-4ba8-bb31-937823f87770/_2020-08-01__5.17.33.png)

```css
<svg width="300" height="200">
    <circle cx="150" cy="100" r="80" fill="green" />
</svg>
```

##### viewbox설정 후 모습

![img](https://images.velog.io/images/myungwoo/post/8e3a0579-554e-4a4d-b2f2-f52f5e86ed7c/_2020-08-01__5.18.22.png)

```css
<svg width="300" height="200" viewBox="0 0 100 100">
    <circle cx="150" cy="100" r="80" fill="green" />
</svg>
```



## SVG tags

#### rect(rectangles) 사각형

화면에 사각형을 그린다. 여기에는 화면상에서 직사각형의 위치와 모양을 제어하는 6가지 기본 속성만 있다. 

`rect` : `x`, `y`,  `width`, `height` , `rx` ,`ry`

* x : 사각형 좌측 상단의 x값을 의미한다.
* y : 사각형 좌측 상단의 y값을 의미한다.
* width : 사각형의 폭을 설정한다.
* height : 사각형의 높이를 설정한다.
* rx,ry : 사각형의 모서리의 radius 값을 말한다.

```css
<svg viewBox="0 0 220 100" xmlns="http://www.w3.org/2000/svg">
  <!-- Simple rectangle -->
  <rect width="100" height="100" />

  <!-- Rounded corner rectangle -->
  <rect x="120" width="100" height="100" rx="15" />
</svg>
```

#### circle

화면에 원을 그린다. circle 요소에 실제로 적용할 수 있는 속성은 세가지가 있다.

`circle` : `r ` , `cx`, `cy`

* r : 원의 반지름을 의미한다.

* cx : 원의 중심중 x값을 의미한다.

* cy ; 원의 중심중 y 값을 의미한다.

  * cx와 cy의 교차점이 해당 circle의 중심점이된다.

    ```css
    <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
      <circle cx="50" cy="50" r="50"/>
    </svg>
    ```

#### ellipse

화면에 타원을 표시한다. 원의 x와 y반경을 개별적으로 확장할 수 있는 `circle` 요소의 좀 더 일반적인 형태이다. (원과는 다르게  x,y방향에대한 각각의 반지름을 가진다.)

`ellipse` : `rx` , `ry` , `cx` ,`cy`

* rx :타원의 x 방향으로의 반지름의 길이를 의미한다.

* ry : 타원의 y 방향으로의 반지름의 길이를 의미한다.

* cx :타원의 중심 중 x 값을 의미한다.

* cy :타원의 중심 중 y 값을 의미한다.

```css
<svg viewBox="0 0 200 100" xmlns="http://www.w3.org/2000/svg">
  <ellipse cx="100" cy="50" rx="100" ry="50" />
</svg>
```

#### line

직선, 선의 시작과 끝지점을 지정하는 두 점을 속성으로 갖는다.

`line` : `x1`, `y1` , `x2` ,`y2`

* x1 : 점 1의 x값이다.
* y1 : 점 1의 y값이다.
  * x1, y1은 line의 시작점
* x2 : 점 2의 x값이다.
* y2 : 점 2의 y값이다.
  * x2, y2는 line의 끝점

선은 시작점부터 끝점까지 그어지게 된다.

```css
<line x1="0" y1="80" x2="100" y2="20" stroke="black" />
```

#### polyline

2개 이상의점들이 직선으로 연결된  도형을그린다. 각 점들의 위치(points) 속성을 설정할 수 있다. 각점(x.y)는 공백으로 구분한다.

`polyline` : `points` 

* points : 점들의 리스트들이다. x,y좌표의 짝으로 이루어져 있으며 좌표들은 쉼표로 구분한다.

```css
  <!-- Example of a polyline with the default fill -->
  <polyline points="0,100 50,25 50,75 100,0" />

  <!-- Example of the same polyline shape with stroke and no fill -->
  <polyline points="100,100 150,25 150,75 200,0"
            fill="none" stroke="black" />
```

#### polygon

다각형, 3개이상의 점들이 연결된 다각형을 그린다. `polyline`과 유사하지만 자동으로 마지막 포인트로부터 첫 번째 포인트로 직선을 만들어서 닫힌 모양을 만든다.

`polygon` : `points` 

* points : 점들의 리스트들이다. x,y좌표의 짝으로 이루어져 있으며 좌표들은 쉼표로 구분한다.

```css
<polygon points="50 160, 55 180, 70 180, 60 190, 65 205, 50 195, 35 205, 40 190, 30 180, 45 180"/>
```

#### path

path는 SVG라이브러리에서 가장 강력한 요소이다. 요소를 사용해서 사각형, 원 , 타원 ,폴리 라인, 다각형을 그릴 수있다. (모든 모양을 만들 수 있다.) 직선으로만 이루어진 도형은 polyline으로도 그릴 수 있지만 곡선을 표시하고 싶다면 path를 사용한다.

##### path d(data)속성

```css
M = move to (이동좌표)
L = line to (선 길이)
H = horizontal line to (수평선)
V = vertical line to (수직선)
C = curve to (곡선)
S = smooth curve to (부드러운 곡선)
Q = quadratic Bézier curve (2차 베지어 곡선)
T = smooth quadratic Bézier curveto (부드러운 2차 베지어 곡선)
A = elliptical Arc(타원형 호)
Z = close path (가까운 경로)
```

* M(m) `M : x y` : 이동하기, 이 명령어는 두 개의 파라미터로 x 와 y좌표를받는다. m명령어는 path의 맨 처음에 그리기를 시작할 위치를 지정한다.

* L(l) `L : x y` : 선 그리기, L명령어는 x,y 두개의 파라미터를 받아서 현재 위치에서 받은 위치로 선을 긋는다.

* H `H : x y` : 가로선 그리기

* V `V: x y` : 세로선 그리기

* Z `Z` : path 닫기, 현 위치에서 시작점으로 직선을 그린다. 항상은 아니지만 path의 끝에 자주 쓰인다. 

  ```css
  <path d="M10 10 H 90 V 90 H 10 Z" fill="transparent" stroke="black"/>
  ```

* C(c) `C : x1 y1, x2 y2, x y` : 큐빅 베지어 곡선, 선을잇는 두 점에 하나씩 제어점을 가지고 있다. 그러므로 곡선을 그리려면 총 세 개의 좌표가 필요하다. 

​		![](https://a11y.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-LDssGNTFE1WzKvtC6X0%2F-LEMzoMMt4Gug4JFcxHV%2F-LEN8iKMpk5B2t27Wuab%2Fimage.png?alt=media&token=eb41de63-279d-455b-9949-bdfb756a516f)

​	

```css
<path d="M10,55 C35,30 80,0 120,55" fill="none" stroke="#333333" stroke-width="3" />
```

* S `S:x2 y2, x y`: 여러 베지어 곡선을연결하여 확장도니 곡선 형태를 만들 수 있다. 한 선의 제어점을 다른 선의 제어잠과 반대방향으로 그어 완만한 경사를 만들어야 할 때가 많은데, 이 경우 사용한다.

​	![](https://a11y.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-LDssGNTFE1WzKvtC6X0%2F-LEMzoMMt4Gug4JFcxHV%2F-LENBi8fi2NWlcGrZCBq%2Fimage.png?alt=media&token=459e8c30-c52f-4d8f-a2fa-636c7171d798)

* Q `Q : x1 x2, x y` : 3차 베지어곡선(C) 보다 간단한 다른 형태의 곡선, 하나의 컨트롤 포인트를 제외하곤 유사하다. 시작과 끝점 사이에 위치한 컨트롤 포인트(`x1 y1`)가 곡선의 모양을 결정한다.

​	![img](https://a11y.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-LDssGNTFE1WzKvtC6X0%2F-LEND2UU4xMGDqPAdrB1%2F-LENFu7ldDzeucddtd8x%2Fimage.png?alt=media&token=4aa3d874-7684-4321-af5d-214055955bd0)

```css
<path 
    d="M20,50 Q60,75 100,50" 
    fill="none" stroke="#b13138" stroke-width="6" stroke-linecap="round" />
```

* T `T : x y` : 2차 베지어곡선(Q)을 연결하는 단축 명령어, 이전에 사용한 제어점(`x1 y1`)으로부터 새로운 제어점을 만들어낸다. 계속 이어서 복잡한 도형을 만들 수 있다.!

​	![img](https://a11y.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-LDssGNTFE1WzKvtC6X0%2F-LEND2UU4xMGDqPAdrB1%2F-LENJhztK43rTXTQI94j%2Fimage.png?alt=media&token=fd90c8b7-3e55-42f1-884e-913eb6977263)

```css
<path d="M10 80 Q 52.5 10, 95 80 T 180 80" stroke="black" fill="transparent"/>
```

* A `A : rx ry (x rotation degree) (large-arc-flag) (sweep-flag) x y `   => `A : rx ry x축-회전각 큰-호-플래그 쓸기-방향 플래그 x y`: 타원형 호 명령은 타원의 호를 그린다. x,y축 반지름이 주어졌을때, 두 점을 연결할 수있는 타원은 2개가 있으며, 각각의 타원에서 두 점을 잇는 패스 또한 2개씩 있기 때문에 어떤 상황에서든 네 종류의 호를 그릴 수 있다. 이러한 성질 때문에 호를 그리는 명령어는 많은 수의 매개 변수를 요구한다.

​	![img](https://a11y.gitbook.io/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-LDssGNTFE1WzKvtC6X0%2F-LEND2UU4xMGDqPAdrB1%2F-LENMi9pt9Ipaw7OSwmQ%2Fimage.png?alt=media&token=8205e35e-c0f5-48a4-bda7-a483933b7658)

```css
<path
      d="M105,20 a20,20 0 1,1 50,25"
      fill="none" stroke="#4286f0" stroke-width="8" />
/*
 패스 데이터 d 에 설정된 값은 시작점(105, 20) 끝점 (50,25) x 축 회전각(0), 큰호플래그(1), 쓸기 방향 플래그(1) 
*/
```

# 채우기, 선 그리기

SVG에서는 `fill`을 사용해서 원하는 색을 채울 수 있다. `stroke` 는 그려진 객체의 둘레의 색깔을 설정할 수 있게 해준다. 색상은 RGB값을 사용가능하다. `opacity` 옵션을 통해 투명도또한 조절이 가능하다(`stroke-opacity, fill-opacity`)

## stroke

도형 선의 색상을 지정하는 속성이다.

* `stroke="colors"` : 선 색 속성

* `stroke-width="numbers"` : 선 굵기 속성

  * 둘레의 두께를 설정할 수 있다.

* `stroke-linecap="butt | round | square"` : 선의 양쪽 끝 모양 속성

  * butt : 라인의 끝에 둘레를 추가하지 않는다. 선 끝으로 딱 자른다.
  * round : 선 끝을 둥글게 처리한다.
  * square : 선 끝을 한번더 네모로 묶음 처리한다.

  ![img](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Fills_and_Strokes/svg_stroke_linecap_example.png)

* `stroke-dasharrt="number, number, number, number...."` : 점선처리 

  * 컴마를 통해 분리하며 홀수번째 자리의 숫자는 선의 길이, 짝수번째 자리 숫자는 공백의 길이를 의미한다.

* `stroke-linejoin="miter | round | bevel"` : 두 라인이 만날 때 어떤 모양으로 선끝을 처리할지 정의한다.

  * miter : 교차하는 선을 정사각형모양의 모서리를 만든다.
  * round : 교차하는 지점을 둥글게 처리한다.
  * bevel : 두 교차에서 확장하기 위해 2개의 각도를 가진 모서리를 만든다.

  ![img](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Fills_and_Strokes/svg_stroke_linejoin_example.png)

## fill

도형에 색상을 채운다.

`fill ; color(rgb ,color names, rgba)`

```css
<circle cx="50" cy="50" r="25"
        style="stroke: none; fill: #0000ff;
               fill-opacity: 0.3;  " />
<circle cx="120" cy="50" r="25"
        style="stroke: none; fill: #0000ff;
               fill-opacity: 0.7;  " />
```

##### CSS 활용하기

SVG 태그안에 `style` 속성을 사용함으로서 CSS문법을 연동해 사용할 수있다. 

```css
 <rect x="10" height="180" y="10" width="180" style="stroke: black; fill: red;"/>
```



-----

references 

https://developer.mozilla.org/ko/docs/Web/SVG/Tutorial

https://ossam5.tistory.com/112?category=897196

https://velog.io/@myungwoo/SVG-%ED%83%90%ED%97%98%ED%95%98%EA%B8%B0

https://a11y.gitbook.io/graphics-aria/svg-graphics/svg-paths-shape