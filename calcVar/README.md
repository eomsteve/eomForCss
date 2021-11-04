# Calc, --var

## --var (CSS변수) 

사용자 지정 속성 (CSS 변수, 종속 변수)은 CSS 저작자가 정의하는 개체로, 문서 전반적으로 재사용할 임의의 값을 담는다. 사용자 지정 속성은 전용 표기법을 사용해 정의하고, 함수를 사용해 접근할 수 있다.

수 백곳의 서로다른위치에서 같은 색상을 사용한다면 그 색상을 바꿔야할 상황이 왔을때 대규모 전역 검색 바꾸기를 피할 수 없다. 또한 식별자를 사용함으로서 RGB 값을 사용하기 보다는 `--main-text-color` 가 이해하기 쉽다는 장점도 가져올 수 있다.

#### 사용법

두개의 붙임표로 시작하는 속성의 이름과 함계, 유효한 CSS값이라면 아무거나 극밧으로 지정해 선언한다. 다른 일반적인 속성과 마찬가지로 사용자 지정 속성도 규칙 집합 내에 작성한다.

**참고**: 사용자 지정 속성의 이름은 대소문자를 구분한다. 따라서 `--my-color`와 `--My-color`는 서로 다른 속성으로 처리된다.

```css
/*특정 요소(범위)에서 변수 선언하기*/
element
{
	--main-text-color : blue;
}
/* 전역변수로 설정하여 모든 요소에서 접근할 수 있다. :root는 루트를 가리키는데 보통 <html> 태그를 뜻한다. */
:root
{
    --main-color : black;
    --main-padding : 50px;
}
/*선언한 변수를 사용하기
사용자 지정 속성의 값을 사용할 대에는 일반적인 값의 자리에 var()함수를 지정하고, 그 매개변수로는 사용자 지정 속성의 이름을 적으면 된다.
*/
element
{
    background-color : var(--main-color);
}
```



## calc

`calc()` CSS 함수를 사용하면 CSS 속성의 값으로 계산식을지정할 수 있다. `length` `frequency` `angle` `time` ` percentage` `number` `integer` 를 받는 속성의 값으로 사용할 수있다. 

```css
/*예문*/
width : calc(100% - 80px);
```

`calc()` 함수는 매개변수로 표현식 하나를 받고, 표현식의 결과가 최종 값이 된다. 표현식은 단순 계산식은 무엇이든 가능하며 표준 연산자 우선 순위를 따른다. ` + - * /`

* `+` 와 `-` 연산자는 좌우에 공백이 있어야 한다. `calc(50% -8px)` 은 백분율 50%와 -8 px의 연속된 인자로 인식하여 유효하지 않다.
* `*` 과 `/`  연산자는 좌우공백을 요구하지 않지만 일관성을위해 추가하는 편이 좋다.
* `calc()` 함수를 중첩해서 사용하면 내부의 `calc()`는 단순한 괄호로 간주한다.

_____

references

calc : https://developer.mozilla.org/ko/docs/Web/CSS/calc()

--var : https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties

