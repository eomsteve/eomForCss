# CSS animation 

CSS 애니메이션은 요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 전환시켜준다. 애니메이션을 나타내는 CSS 스타일과 애니메이션의 중간 상태를 나타내는 키프레임들로 이루어진다.

#### CSS 애니메이션

기존에 사용되던 스크립트를 이용한(`requestAnimationFrame()`, `Animation api`) 애니메이션보다 이점을 가진다.

1. 자바스크립트를 모르더라도 간단하게 애니메이션을 만들 수 있다. 
2. 자바스크립트를 이용한 애니메이션은 잘 만들어졌더라도 성능이 좋지 못할때가 있다. CSS 애니메이션은 frame-skipping 같으 여러 기술을 이용하여 최대한 부드럽게 랜더링 된다.
3. 브라우저는 애니메이션의 성능을 효율적으로 최적화 할 수 있다. 

## animation 적용

* `animation-delay` :  요소가 로드되고 나서 언제 애니메이션이 시작될지 정한다.
* `animation-direction` : 애니메이션이 종료되고 다시 처음부터 시작할지, 역방향으로 진행할지 지정한다.
* `animation-duration` :  한 싸이클의 애니메이션이 얼마에 걸쳐 일어날지 지정한다.
* `animation-iterattion-count` :  애니메이션이 몇 번 반복될지 지정한다. `infinite`로 지정하여 무한히 반복할 수 있다.
* `animation-name` : 이 애니메이션의 중간상태를 지정한다. 중간상태는 `@keyframe` 규칙을 이용하여 기술한다.
* `animation-play-state` : 애니메이션을 멈추거나 다시 시작할 수 있다.
* `animation-timing-function` : 중간 상태의 전환을 어떤 시간간격으로 진행할지 지정한다.

* `animation-fill-mode` :  애니메이션이 시작되기 전이나 끝나고 난 후 어떤값이 적용될지 지정한다.

### animation-delay

**`animation-delay`** 속성은 애니메이션이 시작할 시점을 지정한다. 시작 즉시, 잠시 후에, 또는 애니메이션이 일부 진행한 시점부터 시작할 수 있다.

`animation-delay` : `time` 

* time : 애니메이션이 시작될 요소가 적용되는 순간부터의 시간 오프셋이다. 필수로 들어간다.
  * 양수값은 지정된 시간이 경과후 애니메이션이 시작된다. 음수값을 지정하면 애니메이션이 즉시 시작하지만 애니메이션 시퀀스의 1초부터 시작된다.

```css
/* Single animation */
animation-delay: 3s;
animation-delay: 0s;
animation-delay: -1500ms;

/* Multiple animations */
animation-delay: 2.1s, 480ms;
```

### animation-direction

**`animation-direction`** 속성은 애니메이션이 앞으로, 뒤로 또는 앞뒤로 번갈아 재생되어야 하는지 여부를 지정한다.

`animation-direction` : `normal`| `reverse` | `alternate` | `alternate-revers`  

* normal : 애니메이션이 정방향으로 재생된다. 순환시 시작상태로 재설정 되고 다시 시작된다. 기본값.
* reverse : 애니메이션이 역방향으로 재생된다. 순환시 종료 상태로 재설덩 되고 다시 시작된다. 
* alternate : 애니메이션은 매 사이클마다 주기의 방향을 뒤집으며 첫 번째 방향은 정방향으로 진행된다.
* alternate-reverse : alternate와 같으며, 첫 번째 방향이 역방향으로 진행된다.

```css
/* Single animation */
animation-direction: normal;
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;

/* Multiple animations */
animation-direction: normal, reverse;
animation-direction: alternate, reverse, normal;
```

> 애니메이션이 역방향으로 재생될때는 `animation-timing-function` 속성과 관련된 효과도 반대로 적용된다.

### animation-duration

**`animation-duration`** 속성은 애니메이션이 한 사이클을 완료하는 데 걸리는 시간을 지정한다.

`animation-duration` : `time` 

* time : 애니메이션이 한 사이클을 완료하는데 걸리는 지속시간이다. 값은 양수 또는 0이어야 하며 단위는 필수이다. 

```css
/* Single animation */
animation-duration: 6s;
animation-duration: 120ms;

/* Multiple animations */
animation-duration: 1.64s, 15.22s;
animation-duration: 10s, 35s, 230ms;
```

### animation-iteration-count

**`animation-iteration-count`**  속성은 애니메이션의 재생횟수를 정의하는 속성이다.

`animation-iteration-count` : `infinite`  | `number`

* infinite : 애니메이션이 멈추지않고 계속 반복된다.
* number : 지정된 수 만큼 애니메이션이 반복된다. 기본값은 1이다. 정수값이 아닌 소숫값같은 숫자가 들어오면 숫자만큼의 사이클을 진행한다.

```css
/* Keyword value */
animation-iteration-count: infinite;

/* <number> values */
animation-iteration-count: 3;
animation-iteration-count: 2.4;

/* Multiple values */
animation-iteration-count: 2, 0, infinite;
```

### animation-name

**`animation-name`**  속성은 `@keyframe` 속성에서 설정한 애니메이션의 이름이다. 애니메이션의 이름을 설정해야 재생할 수 있다.

`animation-name` : `none`  | `custom-ident`

* none : 애니메이션을 재생하지 않는다. 설령 `none`이라는 이름의 `@keyframe`이 있더라도 애니메이션을 재생하지 않는다.
* custom-ident(사용자정의) : 이 식별자는 문자, 대소문자 숫자, 언더바(), 대쉬(-)의 조합으로 구성된다. 첫 글자는 문자, 언더바(), 대쉬(-)로 시작해야한다. 

```css
/* Single animation */
animation-name: none;
animation-name: test_05;
animation-name: -specific;
animation-name: sliding-vertically;

/* Multiple animations */
animation-name: test1, animation4;
animation-name: none, -moz-specific, sliding;
```

##### @keyframe

 애니메이션을 재생할 각 프레임의 스타일을 정의하는 것으로, from 속성이나 0% 속성에 설정한 스타일에서 출발해 to 속성이나 100%속성에 설정한 스타일로 점차 바뀌면서 애니메이션이 재생된다.

```css
@keyframes slidein {
  from {
    margin-left: 100%;
    width: 300%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
```

### animation-play-state

**`animation-play-state`**  속성은 애니메이션의 재생여부를 정의한다.

`animation-play-state` : `running`  | `paused`

* running : 애니메이션을 재생한다. 기본값.
* paused : 애니메이션을 정지한다.

```css
/* Single animation */
animation-play-state: running;
animation-play-state: paused;

/* Multiple animations */
animation-play-state: paused, running, running;
```

### animation-timing-function

**`animation-timing-function`**  속성은 애니메이션의 키프레임 사이의 재생속도를 조정하는 속성이다. 재생하는 동안 단계별 재생속도를 설정한다. `transition-timing-function`과 유사하다.

`animation-timing-function` : `ease` | `linear`| `ease-in` | `ease-out` | `ease-in-out` | `cubic-bezier()` | `steps()`

* ease : 기본값, 천천히 시작해서 빠르게 진행하며 천천히 끝낸다.
* linear : 처음과 끝이 같은속도로 나타난다.
* ease-in : 천천히 시작한다.
* ease-out : 천천히 끝닌다.
* ease-in-out : 천천히 시작해서 천천히 끝난다.
* cubic-bezier(n,n,n,n) ; 직접 값을지정할수 있다. 가능한 값은 0부터 1사이의 값이다. 
* steps(n, `jumpterm`) : steps 는 애니메이션을 스텝에 맞게 끊어서 표현해준다. 
  * step-start : : steps(1, start)와 같다. 시작하는 지점에 스텝을 끊어준다.
  * step-end : steps(1,end)와 같다. 끝나는지점에 스텝을 끊어준다.
  * steps(5, end or start) : 5번으로 나누어 끊어지듯 진행됨  만약10초동안 진행되는 애니메이션이라면
    * steps(5,end) 일 경우 -> 2,4,6,8초에 순간적으로 변화
    * steps(5,start) 일 경우 -> 0, 2,4,6,8초에 순간적으로 변화

```css
.ease {
   animation-timing-function: ease;
}
.easein {
   animation-timing-function: ease-in;
}
.easeout {
   animation-timing-function: ease-out;
}
.easeinout {
   animation-timing-function: ease-in-out;
}
.linear {
   animation-timing-function: linear;
}
.cb {
   animation-timing-function: cubic-bezier(0.2,-2,0.8,2);
}
.step-start {
   animation-timing-function: step-start;
}
.step-end {
   animation-timing-function: step-end;
}
```

### animation-fill-mode

**`animation-fill-mode`**  속성은 CSS 애니메이션이 실행전과 후에 대상에 스타일을 적용하는 방법을 정의한다.

`animation-fill-mode` : `none`  | `forwards` | `backwards` |`both`

* none : 애니메이션은 실행되지 않을 때 대상에 스타일을 적용하지 않는다. 다른 css 규칙을 사용하여 표현한다. 기본값.
* forwards : 대상은 실행된 애니메이션의 마지막 프레임에 설정된 계산값을 유지한다. 마지막 키프레임은 `animation-direction` 및 `animation-timing-function` 값에 따라 다르다.(애니메이션이 진행된 후 그 스타일을 유지)
* backwards : 애니메이션은 대상에 적용되는 즉시 첫 번째 키프레임에 정의된 값을 적용하고 `animation-delay` 기간동안 값을 유지한다. (애니메이션이 시작되기전 애니메이션 스타일 유지)
* both : `forwards` `backwards` 모든 규착을 따른다.

```css
/* Single animation */
animation-fill-mode: none;
animation-fill-mode: forwards;
animation-fill-mode: backwards;
animation-fill-mode: both;

/* Multiple animations */
animation-fill-mode: none, backwards;
animation-fill-mode: both, forwards, none;
```

## transition VS animation 차이

transition 속성과 animation 속성은 플래시의 기술이나 자바스크립트의 도움 없이 요소에 직접 애니메이션 효과를 적용하는 속성이다.

transition 속성은 요소의 상태가 변해야 애니메이션을 실행한다.

animation 속성은 요소의 모양과 동작을 키프레임 단위로 변경할 수 있다. 키프레임 동작은 재생 횟수, 재생 방향등 여러 애니메이션 속성으로 제어할 수 있다.

transition 속성과 animation 속성의 가장 큰 차이는 transition 속성은 요소의 상태가 바뀌어야 바뀌는 상태를 애니메이션으로 표현하지만, animation 속성은 요소의 상태 변화와 상관 없이 애니메이션을 실행한다. 또한 `@keyframes` 속성으로 프레임을 추가할 수 있다.

```markdown
CSS3 내의 애니메이션을 사용하면 여러 키프레임에서 요소의 모양과 동작을 변경할 수 있습니다. 전환은 한 상태에서 다른 상태로의 변경을 제공하는 반면 애니메이션은 다른 키프레임에 여러 전환 지점을 설정할 수 있습니다.
```

------

references

https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Animations/Using_CSS_animations

https://webclub.tistory.com/621