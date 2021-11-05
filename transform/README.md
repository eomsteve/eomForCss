# Transform

CSS transform속성으로 요소에 회전, 크기조절, 이동효과를 부여할수 있다. 

`transform` 은 CSS 시각적 모델좌표공간을 변경한다.

transform 속성은 HTML 요소에 대해 다음과 같은 동작을 한다.

* 해당 요소를 움직인다.
* 해당 요소를 회전한다.
* 해당 요소의 크기를 변경한다.
* 해당 요소를 기울인다.
* 해당 요소에 위의 네 가지 동작중 원하는 동작을 한번에 적용시킨다.

### translate()

`translate()` 메소드는 현재 위치에서 해당 요소를 주어진 x축과 y축의 거리만큼 이동시킨다. 주어진거리가 양수이면 해당 축의 양의 방향으로, 음수이면 해당 축의 음의 방향으로 이동시킨다.

### rotate()

`rotate()` 메소드는 해당 요소를 주어진 각도만큼 시계방햐이나 반시계 방향으로 회전시킨다. 주어진 각도가 양수이면 시계방향으로, 음수이면 반시계방향으로 회전시킨다.

### scale()

`scale()` 메소드는 해당 요소의 크기를 주어진 배율만큼 늘리거나 줄인다.

주어진 배율이 1보다 크면 크기를 늘리고, 0보다 크고 1보다 작으면 크기를 줄인다.

#### skewX() 메소드

`skewX()` 메소드는 해당 요소를 주어진 각도만큼 x축 방향으로 기울인다.

주어진 각도가 양수이면 x축의 양의 방향으로, 음수이면 x축의 음의 방향으로 기울인다.

#### skewY() 메소드

`skewY()` 메소드는 해당 요소를 주어진 각도만큼 y축 방향으로 기울인다.

주어진 각도가 양수이면 y축의 양의 방향으로, 음수이면 y축의 음의 방향으로 기울인다.

#### skew() 메소드

`skew()` 메소드는 해당 요소를 주어진 각도만큼 각각 x축과 y축 방향으로 기울인다.

#### matrix() 메소드

`matrix()` 메소드는 모든 transform 메소드를 한 줄에 설정할 수 있도록 해준다.

matrix 메소드의 순서는 다음과 같다.

matrix(**scaleX()**, **skewY()**, **skewX()**, **scaleY()**, **translateX()**, **translateY()**);

```css
/* 키워드 값 */
transform: none;

/* 함수 값 */
transform: matrix(1.0, 2.0, 3.0, 4.0, 5.0, 6.0);
transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
transform: perspective(17px);
transform: rotate(0.5turn);
transform: rotate3d(1, 2.0, 3.0, 10deg);
transform: rotateX(10deg);
transform: rotateY(10deg);
transform: rotateZ(10deg);
transform: translate(12px, 50%);
transform: translate3d(12px, 50%, 3em);
transform: translateX(2em);
transform: translateY(3in);
transform: translateZ(2px);
transform: scale(2, 0.5);
transform: scale3d(2.5, 1.2, 0.3);
transform: scaleX(2);
transform: scaleY(0.5);
transform: scaleZ(0.3);
transform: skew(30deg, 20deg);
transform: skewX(30deg);
transform: skewY(1.07rad);

/* 다중 함수 값 */
transform: translateX(10px) rotate(10deg) translateY(5px);
transform: perspective(500px) translate(10px, 0, 20px) rotateY(3deg);

/* 전역 값 */
transform: inherit;
transform: initial;
transform: unset;
```

## 정렬

CSS 정렬속성은 `flex` 컨테이너의 기본축과 `grid`컨테이너의 인라인 축을 다라 공간에 정렬한다.

`justify` 는 수평축으로의 정렬(가로축을 기준으로 좌우에 대한 정렬을 뜻함.) `align` 은 수직축(세로축)으로의 정렬이다.

### justify-content

```css
.container {
	justify-content: start;
	/* justify-content: end; */
	/* justify-content: center; */
	/* justify-content: space-between; */
	/* justify-content: space-around; */
	/* justify-content: space-evenly; */
}
```

* start : 아이템들을 시작점으로 정렬한다.
* end : 아이템들을 끝점으로 정렬한다.
* center :  아이템들을 가운데로 정렬한다.
* space-between : 아이템들의 사이에 균일한 간격을 만들어준다.
* space-around : 아이템들의 둘레에 균일한간격을 만들어준다.
* space-evenly : 아이템들의 사이와 양 끝에 균일한 간격을 만들어 준다. 

### align-item

```css
.container {
	align-items: stretch;
	/* align-items: start; */
	/* align-items: end; */
	/* align-items: center; */
	/* align-items: baseline; */
}
```

* stretch (기본값) : 아이템들이 수직축방향으로 끝까지 늘어난다.
* start : 아이템들을 시작점으로 정렬한다. 
* end : 아이템들을 끝점으로 정렬한다.
* center :  아이템들을 가운데로 정렬한다.
* baseline : 아이템들은 텍스트 베이스라인 기준으로 정렬한다.



-----

references

https://developer.mozilla.org/ko/docs/Web/CSS/transform

http://tcpschool.com/css/css3_transform_2Dtransform

https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content