# FLEX CSS

flex css 속성은 하나의 플렉스 아이템이 자신의 컨테이너 차지하는 공간에 맞추기 위해 크기를 키우거나 줄이는 방법을 설정하는 속성이다. 

레이아웃 배치 기능으로 고안되었으며, float와 inline-block 등을 이용한 기존 방식보다 강력하고 편리한 기능들이 많다. 

flex 값에는 auto, initial, none 이나 단위없는 양의 수를 사용해야한다. 

기본적으로 플렉스 아이템은 콘텐츠의 최소 너비 미만으로 줄어들지 않는다.

* flex-grow(성장) 는 flex 요소가  flex 컨테이너 요소 내부에서 할당 가능한 공간의 정도를 선언한다. 
  * 형제요소로 렌더링된 아이템들이 동일한 flex-grow 값을 갖느다면 flex-container 내부에서 동일한 공간을 할당 받는다. 
  * flex-grow 값으로 다른 값을 지정한다면 그에 따라 다른 공간값을 나누어 할당받게 된다.
* flex-shrink(수축) 는 flex요소의 크기가 flex-container요소의 크기보다 클때 flex-shrink속성을 사용하는데, 설정된 숫자값에 따라 flex요소의 크기가 축소된다.

* flex-basis 속성은 플렉스 아이템의 초기 크기를 지정한다. box-sizing 을 따로 지정하지 않는다면 코텐츠 박스의 크기를 변경한다.
* flex-direction 속성은 플렉스 컨테이너 내의 아이템을 배치할 때 사용할 주축 및 방향( 정방향, 역방향)을 지정한다.
  * row : 왼쪽에서 오른쪽으로(작성하는 방향)
  * row-reverse : row의 역방향
  * column : 쌓이는 방향대로
  * column-reverse : column방향의 역방향

```css
/* Keyword values */
flex: auto;
flex: initial;
flex: none;

/* One value, unitless number: flex-grow */
flex: 2;

/* One value, length or percentage: flex-basis */
flex: 10em;
flex: 30%;

/* Two values: flex-grow | flex-basis */
flex: 1 30px;

/* Two values: flex-grow | flex-shrink */
flex: 2 2;

/* Three values: flex-grow | flex-shrink | flex-basis */
flex: 2 2 10%;

/* Global values */
flex: inherit;
flex: initial;
flex: unset;
```

flex아이템들은 가로 방향으로 배치되고 자신이 가진 내용물의 width 만큼만 차지하게 된다. 

## 정렬

`justify` 는 수평축으로의 정렬(가로축을 기준으로 좌우에 대한 정렬을 뜻함.) `align` 은 수직축(세로축)으로의 정렬이다.

### justify-content

```css
.container {
	justify-content: flex-start;
	/* justify-content: flex-end; */
	/* justify-content: center; */
	/* justify-content: space-between; */
	/* justify-content: space-around; */
	/* justify-content: space-evenly; */
}
```

* flex-start : 아이템들을 시작점으로 정렬한다. (flex-direction이 row일때는 왼쪽, column일때는 위)
* flex-end : 아이템들을 끝점으로 정렬한다. (flex-direction이 row일때는 오른쪽, column일때는 아래)
* center :  아이템들을 가운데로 정렬한다.
* space-between : 아이템들의 사이에 균일한 간격을 만들어준다.
* space-around : 아이템들의 둘레에 균일한간격을 만들어준다.
* space-evenly : 아이템들의 사이와 양 끝에 균일한 간격을 만들어 준다. 

![](https://studiomeal.com/wp-content/uploads/2020/01/10-1.jpg)

### align-item

```css
.container {
	align-items: stretch;
	/* align-items: flex-start; */
	/* align-items: flex-end; */
	/* align-items: center; */
	/* align-items: baseline; */
}
```

* stretch (기본값) : 아이템들이 수직축방향으로 끝까지 늘어난다.
* flex-start : 아이템들을 시작점으로 정렬한다. (flex-direction이 row일때는 **위**, column일때는 **왼쪽**)
* flex-end : 아이템들을 끝점으로 정렬한다. (flex-direction이 row일때는 **아래**, column일때는 **오른쪽**)
* center :  아이템들을 가운데로 정렬한다.
* baseline : 아이템들은 텍스트 베이스라인 기준으로 정렬한다.

-----

references

https://developer.mozilla.org/ko/docs/Web/CSS/flex

https://studiomeal.com/archives/197