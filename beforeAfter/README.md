# 가상 요소와 가상 클래스

CSS 가상요소는 선택자로 선택한 요소의 뒤에 붙여 표기하는 미리 약속된 키워드를 말한다. 요소의 특정한 부분에 정해진 기능을 하도록 가상 요소 키워드별로 미리 기능이 정의되어 있으며, 요소에 CSS 속성을 적용하는것과 같은 방법으로  다양한 CSS 속성을 적용할 수 있디 대문에 마치 하나의 하위 요소처럼 사용할 수 있어 가상 요소라고 한다.

가상 요소는 다음 6가지가 있다.

| **가상 요소**  | **설명**                                                     |
| -------------- | ------------------------------------------------------------ |
| ::before       | 요소 내용 앞쪽에 새 컨텐츠를 추가.                           |
| ::after        | 요소 내용 끝에 새 컨텐츠를 추가.                             |
| ::selection    | 마우스 드래그로 선택한 텍스트 컨텐츠 영역을 선택.            |
| ::marker       | 목록 아이템 앞에 붙는 마커를 선택.                           |
| ::first-letter | 현재 웹 브라우저에 보이는 상태를 기준으로 요소의 텍스트 컨텐츠 첫 글자를 선택. |
| ::first-line   | 현재 웹 브라우저에 보이는 상태를 기준으로 요소의 텍스트 컨텐츠 첫 줄 내용을 선택. |

# after

CSS에서 `::after` 는 선택한 요소의 맨 마지막 자식으로 가상 요소를 생성한다. 보통 content속성과 함께 짝지어, 요소에 장식용 콘텐츠를 추가할 때 사용한다. 기본값은 인라인이다.

```css
/* 링크 뒤에 화살표 추가 */
a::after {
  content: "→";
}
```

# before

CSS에서 `::before` 는 선택한 요소의 첫 자식으로 가상요소를 하나생성한다. 보통 content속성과 함게 짝지어, 요소에 장식용 콘텐츠를 추가할 때 사용한다. 기본값은 인라인이다.

```css
/* 링크 앞에 하트 추가 */
a::before {
  content: "♥";
}
```

## 가상 요소의 컨텐츠 표시위치

`::before` 와 `::after` 가상요소로 추가한 콘텐츠는 일반 HTML 태그 요소처럼 배치 속성을 사용해 자유룝게 배치할 수 있다. 

**가장 중요한 가상 요소의 생성 위치는 ::before 가상요소 -> 요소의 콘텐츠 -> ::after 가상요소 순서이다.**

```html
<h1>
	h1::before
	"CSS 가상요소"
	h1::after
</h1>
```

## 가상요소에 동적 컨텐츠 표시

`::before` 와 `::after` 가상요소 content속성에는 HTML 태그의 속성값을 가져오는 `attr()` 함수를 사용할 수 있다. 특히 데이터 속성값(`data-`)을 가져올 수 있기 때문에 컨텐츠에 표시하는 동적인 내용들을 다루고 관리하기가 수월해진다. 

```html
<button classs="coupon" data-userName="eom"></button>
<style>
	button.coupon::before
	{
		content : attr(data-userName) "님을 위한 쿠폰";
	padding : 10px 20px;
	}
</style>
```

표시할 컨텐츠 내용을 수정하기위해 HTML을 수정할 필요가 없고, 동적인 데이터 부분만 태그 속성으로 따로 관리하기 때문에 데이터의 관리도 편해진다. 

-----

references

https://blogpack.tistory.com/1025

after : https://developer.mozilla.org/ko/docs/Web/CSS/::after

before : https://developer.mozilla.org/ko/docs/Web/CSS/::before

