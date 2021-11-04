# CSS Grid

CSS 그리드 레이아웃은 페이지를 여러 주요 영역으로 나누거나 크기와 위치 및 문서 계층 구조의 관점에서 HTML 기본 요소로 작성된 컨드롤 간의 관계를 정의하는데 탁월하다.

CSS그리드는 2차원의 레이아웃 시스템을 제공한다.

 `flex` 와 `grid` 는 컨테이너와 아이템 구조를 사용하는점에서 같다. 그리고 설정한 방향으로 아이템을 배치한다는 점도 같다. 한편 `flex`는 *단일 축을따라 레일 위에 아이템을 쌓는 방식*인데 `grid`는 2개 축을 모두 활용하여 격자위에 아이템을 배치하는점이 다르다.

![](https://studiomeal.com/wp-content/uploads/2020/01/01-1.jpg)

> flex에 익숙하지 않다면 flex에 익숙해진 후 grid를 학습하길 권한다.

## CSS grid layout 문법과 예제

### grid

gird속성은 `grid-template` , `grid-auto` 속성의 단축 속성이다. 하위 속성의 명세를 알고 있어야 단축 속성을 사용 할 수 있다.

>  fr = fraction : 일부, 적은 ,( 수학) 분수 1fr 1fr 1fr 은 균일한 1:1:1 비율로 만든다는 뜻이다.

```css
/* <'grid-template'> values */
grid: none;
grid: "a" 100px "b" 1fr;
grid: [linename1] "a" 100px [linename2];
grid: "a" 200px "b" min-content;
grid: "a" minmax(100px, max-content) "b" 20%;
grid: 100px / 200px;
grid: minmax(400px, min-content) / repeat(auto-fill, 50px);

/* <'grid-template-rows'> / <'grid-auto-columns'>*/
grid: 200px / auto-flow;
grid: 30% / auto-flow dense;
grid: repeat(3, [line1 line2 line3] 200px) / auto-flow 300px;
grid: [line1] minmax(20em, max-content) / auto-flow dense 40%;

/* [ auto-flow && dense? ] <'grid-auto-rows'>? /
   <'grid-template-columns'> values */
grid: auto-flow / 200px;
grid: auto-flow dense / 30%;
grid: auto-flow 300px / repeat(3, [line1 line2 line3] 200px);
grid: auto-flow dense 40% / [line1] minmax(20em, max-content);

/* Global values */
grid: inherit;
grid: initial;
grid: unset;
```

* grid-template : `grid-template-rows`,`grid-template-column`,`grid-template-areas` 의 단축 속성이다. 그리드 행,열 의 수와 크기에 관여한다.

  * none : `grid-template-rows`,`grid-template-column`,`grid-template-areas`값들의 초기값들을 none으로 설정한다.

  * [ <‘grid-template-rows’> / <‘grid-template-columns’> ]  : 슬래시를기준으로 왼쪽은 행의 값, 오른쪽은 열의 값이다. 이와같이 선언하게 된다면 `grid-template-rows/columns` 값을 선언하는 형식이다.

    * ```css
      /* 이런 형식으로 표현할 수 있고 */
      grid-template: 80px / 160px 1fr auto;
      grid: 80px / 160px 1fr auto;
      
      /* 아래와 같다 */
      grid-template-rows: 80px;
      grid-template-columns: 160px 1fr auto;
      grid-template-areas: none;
      ```

  * `grid-template-rows` 속성과 `grid-template-column` 속성은 세가지 형식의 값 `none` | `<track-list>` | `<auto-track-list>` 중하나의 값 형식을 선언할 수 있는데 초기값은 `none`이다.

  #### repeat 함수

  repeat함수는 반복되는값을 자동으로 처리할 수 있는 함수이다. 

  `repeat()` 함수의 첫 번째인자는 반복 횟수이고, 두 번째 인자는 트랙 목록으로 하나 이상의 크기 값을 공백으로 분리하여 나열할 수 있다.

  `gird-template-areas` 속성은 격자에 '셀 이름'을  생성한다. 생성한 셀 이름은 그리드 아이템을 제어하는 그리드 배치 속성(grid-area)에서 참조할 수 있다. 격자 전체의 구조를 문자로 시각화하여 이해하기 쉬운 장점이 있다.

  ```css
  grid-template-rows: 80px 120px;
  grid-template-columns: repeat(2, 80px 1fr);
  /* ⬇️ 간결하게 표현할 수 있다. */
  grid: 80px 120px / repeat(2, 80px 1fr); 👏
  
  /* 좌우가 같은 표현이다. */
  repeat(5, 1fr) == 1fr 1fr 1fr 1fr 1fr
  repeat(2, auto) == auto auto
  160px repeat(2, auto) == 160px auto auto
  160px repeat(2, 80px 1fr) == 160px 80px 1fr 80px 1fr
  ```

  #### minmax 함수

  최솟값과 최댓값을 지정할 수 있는 함수이다. 

  minmax(100px, auto)의 의미는 최소한 100px, 최대는 자동(auto)으로 늘어나게 한다는 의이이다. 즉 내용의 양이 아무리 적더라도 최소한 높이 100px은 확보하고, 내용이 많아 100px이 넘어가면 알아서 늘어나도록 처리한다 라는 의미이다.

  #### auto-fill 과 auto-fit

  auto-fill과 auto-fit은 column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채운다. 

  * auto-fit은 남은 공간이 있을경우 공간을 채운다.
  * auto-fill은 가능한 많이 채우는 방법으로 공간을 채운다. 빈공간은 그대로 둔다.

### grid-template-row, grid-template-columns

공백으로 구분된 값 리스트를 해석하여 그리드 행, 열을 설정한다. 각 값은 트랙의 크기를 뜻한다.

```CSS
.grid-container {
  grid-template-rows: 25% 100px auto;
  grid-template-columns: 40px 50px auto 50px 40px;
  }
```

![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LH1dN99ZXtZTFG_0JKV%2F-LH6G0OQpsVhg5lSIwqa%2F-LH6GjZk38tS0WNGmbW2%2Fimage.png?alt=media&token=eb54ee29-0a1d-4bf1-be6c-980c769e16ca)

### grid-area

`gird-template-areas` 속성은 격자에 '셀 이름'을  생성한다. 생성한 셀 이름은 그리드 아이템을 제어하는 그리드 배치 속성(grid-area)에서 참조할 수 있다. 격자 전체의 구조를 문자로 시각화하여 이해하기 쉬운장점이 있다.

격자에 셀 이름이 없어도 암시적으로 생성된 줄 번호를 참조하면 아이템을 배치하고 병합할 수 있기 때문에 이속성을 필수라고 생각하지 않아도 된다.

![](https://studiomeal.com/wp-content/uploads/2020/01/08-2.jpg)

```css
.container {
	grid-template-areas:
		"header header header"
		"   a    main    b   "
		"   .     .      .   "
		"footer footer footer";
}
```

`grid-template-areas` 속성을 꼭 사용해야 할 이유가 없다면 아래와 같이 간결하게 `grid` 단축 속성으로 선언하는 것을 권장한다.

```css
grid:
  'header header header'
  'nav    main   main'
  '.      .      .'
  'footer footer footer' / 1fr 2fr 3fr;

/* 아래 세 줄은 모두 익명의 셀을 생성하며 결과가 같다 */
grid: '. . .' / 1fr 2fr 3fr;
grid: auto / 1fr 2fr 3fr;
grid: none / 1fr 2fr 3fr;
```

각 영역의 이름을 매칭하기위해 해당 아이템 요소에 `grid-area` 속성으로 이름을 지정해 주면된다. 

```css
.header { grid-area: header; }
.sidebar-a { grid-area: a; }
.main-content { grid-area: main; }
.sidebar-b { grid-area: b; }
.footer { grid-area: footer; }
```



#### grid-auto-row, grid-auto-columns

그리드의 행/열 크기를 자동으로 조절한다.

`grid-template-rows` / `grid-template-columns`  

사용작가 명시적으로 행/열 템플릿 속성을 설정하면 그리드 트랙 크키로 적용된다.

```css
.grid-container {
  grid-template-rows: repeat(2, 60px);
  grid-template-columns: 90px 90px;
}	
```

![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LH1dN99ZXtZTFG_0JKV%2F-LH85n5sc72uXdJzq2sS%2F-LH88PnbI8ZV90J1A44v%2Fimage.png?alt=media&token=90545693-b92a-4673-911c-5c741cb67668)



#### grid-auto-flow

아이템이 자동으로 배치되는 흐름을 결정하는 속성이다.

그리드에 명시적으로 배치되지않은 아이템이 있을경우, 자동배치 알고리즘이 실행되여 자동으로 배치되도록 설정할 수 있다.

`grid-auto-flow` : row | column;

### gap

그리드 라인(행/열) 사이 간격을 조정한다.

```css
.grid-container {
  grid-template-rows: 80px auto 80px;
  grid-template-columns: 100px 50px 100px;
  /* 행 사이 간격 설정 */
  row-gap: 10px;
  /* 열 사이 간격 설정 */
  column-gap: 15px;
}
```

![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LH1dN99ZXtZTFG_0JKV%2F-LH6qxqVgEPLTSSk3JXq%2F-LH6sNXt4TAdBUxJ7cQW%2Fimage.png?alt=media&token=02a5067e-ca71-4045-b29e-f5ee15b4ad3f)

gap:의값을 1개만 입력하면 행/열 사이의 간격이 동일하게 설정된다.

## 정렬

### Box 정렬의 핵심 개념

* 위치 정렬 : `start`, `end` , `center`와 같은 키워드
* 기본 정렬 : `baseline`키워드와 `first`/`last`  수정자
* 분산정렬 : `stretch` , `space-between` , `space-around` , `space-evenly`

#### 세로 방향 정렬 align-items

아이템들을 세로 (column)방향으로 정렬한다. 컨테이너에 적용한다.

```css
.container
{
	align-items : stretch; // 크기에 맞게 최대한 늘림
    align-items : start; // 위에서부터 시작
    align-items : center; // 중앙
    align-items : end; //아래부터
}
```

#### 가로 방향 정렬 justify-items

아이템들을 세로 (column)방향으로 정렬한다. 컨테이너에 적용한다.

```css
.container
{
	justify-items : stretch; // 크기에 맞게 최대한 늘림
    justify-items : start; // 왼쪽에서부터
    justify-items : center; // 중앙
    justify-items : end; //오른쪽부터
}
```

#### place-items

align-items 와 justify-items를 같이 쓸수 있는 단축 속성이다. 

align-items, justify-items의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용된다.

```css
.container {
	place-items: center start;
}
```

#### 아이템 그룹 세로 정렬 align-content

Grid 아이템들의 높이를 모두 합한 값이 Grid 컨테이너의 높이보다 작을 때 Grid 아이템들을 통째로 정렬한다.

```css
.container {
	align-content: stretch;
	/* align-content: start; */
	/* align-content: center; */
	/* align-content: end; */
	/* align-content: space-between; */
	/* align-content: space-around; */
	/* align-content: space-evenly; */
}
```

#### 아이템 그룹 가로 정렬 justify-content

Grid 아이템들의 너비를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬한다.

```css
.container {
	justify-content: stretch;
	/* justify-content: start; */
	/* justify-content: center; */
	/* justify-content: end; */
	/* justify-content: space-between; */
	/* justify-content: space-around; */
	/* justify-content: space-evenly; */
}
```

#### place-content

align-content와 justify-content를 같이 쓸 수 있는 단축 속성.
align-content, justify-content의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용된다.

```css
.container {
	place-content: space-between center;
}
```

#### 개별 아이템 세로 정렬 align-self-ms-grid-row-align

해당 아이템을 세로(column축) 방향으로 정렬합니다. 아이템에 적용한다.

```css
.item {
	align-self: stretch;
	/* align-self: start; */
	/* align-self: center; */
	/* align-self: end; */
}
```

#### 개별 아이템 가로 정렬 justify-self-ms-grid-column-align

해당 아이템을 가로(row축) 방향으로 정렬합니다. 아이템에 적용한다.

```css
.item {
	justify-self: stretch;
	/* justify-self: start; */
	/* justify-self: center; */
	/* justify-self: end; */
}
```

#### place-self

align-self와 justify-self를 같이 쓸 수 있는 단축 속성.
align-self, justify-self의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용된다.

```css
.item {
	place-self: start center;
}
```

-----

references

https://naradesign.github.io/css-grid-layout.html

https://studiomeal.com/archives/533

https://yamoo9.gitbook.io/css-grid/