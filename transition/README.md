# Transition

 CSS 트랜지션은 CSS 속성을 변경할 때 애니메이션 속도를 조절하는 방법을 제공한다. 속성 변경이 즉시 영향을 미치게 하는 대신, 그 속성의 변화가 일정 기간에걸쳐 일어나도록 할 수 있다. 

두 상태 사이의 트랜지션을 포함하는 애니메이션을  종종 암묵적 트랜지션이라고 부르는데, 이는 시작과 오료 상태 사이의 상태를 브라우저가 암무적으로 정의하기 때문이다.

CSS transitions는 어떤 속성을 움직이게 할지, 딜레이를 설정해서 언제 애니메이션이 시작할지, 지속 시간을 설정해서 트랜지션을 얼마나 지속할지, 그리고 어떻게 트랜지션을 실행하는지 결정하게 한다.

etc. transition은 한 가지 상태에서 다른 상태로 변화하는 것.

## transition property

### transition 

아래 네가지 속성의 단축속성

 	1. 해당 요소에 추가할 `transition` 효과를 설정한다.
 	2. 추가할 전환 효과가 지속될 시간을 설정한다.

```css
transition : transition-property | transition-duration | transition-delay | transition-timing-function
```

* transition-property : css 속성을 지정한다.
* transition-duration : 트렌지션 실행시간
  * 이 속성은 항상 지정해 주어야 한다. 
  * 기본값은 0s인데 이러면 효과가 나타나지 않는다.
* transition-delay : 언제 트랜지션을 시작할지 지정한다.
* transition-timing-function : 트랜지션이 실행되는 동안 속도를 설정한다.

```css
.transition
{
	width : 100px;
	transition : width 3s;
}

.transition:hover
{
	width : 200px;
}
/*요소에 마우스를 올리면 3초동안 넓이가 100px에서 200px로 늘어난다.*/
```

### transition-property

어떤 속성에 트랜지션 효과를 적용할지를 지정한다.

`transition-property`  : `none` |` all` | `property`

* all : 기본값, 모든 속성에 트랜지션 효과가 나타난다.
* none : 아무 속성도 트랜지션 효과가 나타나지 않는다.
* property : 트랜지션 효과를 적용하고싶은 css 속성(하나 이상의 속성을 나열할때 쉼표로 분리한다.

> - `background-color`
> - `background-position`
> - `border-color`
> - `border-width`
> - `border-spacing`
> - `bottom`
> - `clip`
> - `color`
> - `crop`
> - `font-size`
> - `font-weight`
> - `height`
> - `left`
> - `letter-spacing`
> - `line-height`
> - `margin`
> - `max-height`
> - `max-width`
> - `min-height`
> - `min-width`
> - `opacity`
> - `outline-color`
> - `outline-offset`
> - `outline-width`
> - `padding`
> - `right`
> - `text-indent`
> - `text-shadow`
> - `top`
> - `vertical-align`
> - `visibility`
> - `width`
> - `word-spacing`
> - `z-index`

### transition-duration

트랜지션을 완수하는데 걸리는 시간

`transition-duration` : `time`

time 기본값은 0s이다. 단위는 초, 밀리세컨즈 단위로 지정하며 음수는 불가능하다.

```css
transition-property : width, font-size;
transition-duration : 3s, 5s; 
/*width에 3초 font-size에 5초가 부여된다. 마찬가지로 쉼표로 구분*/
```

### transition-timing-function

트랜지션 효과가 진행하는 동안의 속도 변화를 지정한다.

`transition-timing-function` : `ease` | `linear`| `ease-in` | `ease-out` | `ease-in-out` | `cubic-bezier()`

* ease : 기본값, 천천히 시작해서 빠르게 진행하며 천천히 끝낸다.
* linear : 처음과 끝이 같은속도로 나타난다.
* ease-in : 천천히 시작한다.
* ease-out : 천천히 끝닌다.
* ease-in-out : 천천히 시작해서 천천히 끝난다.
* cubic-bezier(n,n,n,n) ; 직접 값을지정할수 있다. 가능한 값은 0부터 1사이의 값이다. 

### transition-delay

언제 트랜지션 효과를 시작할지 설정한다.

`transition-delay` : `time`

* time : 트랜지션 효과가 시작되기 전 기다리는 시간

------

references

https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions

https://aboooks.tistory.com/383