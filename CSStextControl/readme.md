# CSS : 텍스트 제어

### FONT SIZE

`font-size` 속성은 폰트의 크기를 지정한다. 

* 기본값 : `medium` = 12pt, 16px, 1em,100%
* 상속이 가능하다.

#### 절댓값

* `xx-small`
* `x-small`
* `small`
* `medium`
* `large`
* `x-large`
* `xx-large`

#### 연계되어 크기가 변하는값

*  `smaller` : 상위 요소에 비해 상대적으로 더 작은 크기
* `larger ` : 상위 요소에 비해 상대적으로 더 큰 크기

### FONT SIZE에서  EM REM PX의 차이

* pixel(`px`) : 고정된 크기의 단위 (1px = 점 하나)

* point(`pt`) : 고정된 크기의 단위

* `em` : 웹 문서에서 사용되는 단위, 컴퓨터 외 다른 장치에서도 크기 조정이 가능하다.(em 은 대문자 M의 크기를 뜻한다.)

  * 만약 `body` 엘리먼트의 폰트 사이즈를 20px로 정한경우 1em = 20px 이고 2em = 40px입니다. 

  * `em` 은 자동적으로 폰트의 크기를 적용 해 주기 때문에 CSS에서 유용하게 쓰인다.

  * > ```html
    > body {
    >   font-size: 62.5%; /* font-size 1em = 10px 브라우저의 기본 설정 */
    > }
    > span {
    >   font-size: 1.6em; /* 1.6em = 16px */
    > }
    > <div>
    > <span>Outer<span>inner</span>outer</span>
    > </div>
    > ```

    * `span` 태그 안에 `span` 태그를 넣고 `em` 속성을 넣어주면 결과는 
    * `span` 안의 inner 부분이 커져

    ![em](C:\Users\mingy\AppData\Roaming\Typora\typora-user-images\image-20210820001310916.png)

    이러한 결과가 나온다.  브라우저의 기본 폰트  크기가 16px 이라고 가정하면 outer 는 16px로 그려지고, inner 는 25.6px로 그려지는데,  `span` 의 폰트 크기가 `1.6em` 으로 부모의 폰트에 상대적인데, 그 부모의 폰트도 상대적으로 계산되기 때문이다. 이를 **합성** 이라고 한다.

* rem : rem값은 em의 **합성** 문제를 개선하기위해 나왔다. rem값은 부모 엘리먼트가 아니라 **최상위 html엘리먼트에 상대적으로 동작한다.**

* percent(%) : em과 비슷하게 다른 장치에 상대적으로 크기 조절이 가능하다.

   

### FONT WEIGHT

글꼴 굵기를 지정하는 font-weight 속성이다.  

단순의 글씨체의 굴기를 명시하는것 보다 그 가중치에 맞는 폰트를 가져오는것이다.

* `nomal` : 가중치 400과 같다 (디폴트 값)
* `bold`  : 굵은 폰트, 가중치 700과 같다.
* `lighter` : 부모 요소보다 얇은 폰트 가중치(가능할 경우)
* `bolder` : 부모 요소보다 굵은 폰트 가중치(가능할 경우)
* `number` : 100, 200, 300, 400, 500, 600, 700, 800, 900 숫자형 가중치

### COLOR

text및 `text-decoration`, `currentcolor` 현재 색상값을 설정한다. 

> currentcolor : 다른속성에서 사용 할 수 있는 간접적인 값이다. 즉 이 키워드를 통해 다른속성이 color 속성값을 따른다. 상속받은 color속성에서 대신 가져온다. 

* named color 값
  * red, orange, green....
* hex-color 값
  * \#00ff00 #ffffff .....
* rgb값
  * rgb(34, 12, 64, 0.6);
* hsl(hsl : Hue(색생) Saturation(채도) Lightness(명도))값
  * hsl(30.0 100% 50% / 60%) 마지막은 투명도

### TEXT EMPHASIS 

텍스트에 강조 표시를 적용한다(강조점). 단 공백 및 제어문자는 제외한다.

강조점은 상속이 되므로 하위 항목에 대한강조 표시를 변경할 수있다. 

* `none` : 기본값, 강조표시 없음
* `문자열` : 'x','f' 등등
* `keyword value` : `filled` , `open` , `filled sesame`, `open sesame` ,`dot` ,`circle` ,`double-circle` , `triangle` 
* 색상추가 : `filled sesame # 555`

The text-emphasis property is not supported in any of the major browsers.

### OVERFLOW WRAP

어떤 문자가 내용 칸 밖으로 넘치지 않게 속성을 지정한다. word break와 달리 전체 단어를 오버 플로우 없이 한줄에 배치할 수없는 경우에만 줄바꿈을 시행한다.

* `normal` : 보통의 줄바꿈 지점(두 단어 사이의 공백, break point)에서만 줄을 바꾼다. 만약 단어가 너무 길다면 칸 밖으로 나갈 수 있다. 
* `break-word` : 요소의 경계에서 break point가 아니어도 줄바꿈을 한다. 단어가 칸을 넘어가게 되면 단어를 잘라서라도 줄바꿈을 시행한다.

### TEXT DECORATION

선으로 텍스트를 꾸미는 속성이다. (밑줄)

* `none` : 선을 만들지 않는다. 
* line 
  * `underline` : 밑줄을 만든다.
  * `overline` : 글자 위에 선을 만든다.
  * `line-through` : 글자 중간에 선을 만든다. 
* color : 줄에 색상을 넣을 수있다. 
* style  : 선을 긋는 스타일 속성이다. 물결, 점선, 이중선등을 지정할 수 있다.
  * `solid` : 기본, 한줄을 긋는다.
  * `double` : 2중선을 긋는다.
  * `dotted` :  점선을 긋는다.
  * `dashed` : -- -- -- --이런 모양의 선을 만든다.
  * `wavy` : 물결선을 만든다.
* thickness : 선의 굵기를 지정한다.

### TEXT ALIGN

텍스트의 정렬 방향을 의미한다. 

* `left` : 왼쪽정렬
* `right` : 오른쪽 정렬
* `center` : 가운데 정렬
* `justify` : 양쪽정렬(줄 상자의 왼쪽과 오른쪽 끝에 텍스트를 맞추기 위해 공간을 띄움)

-----

references

font-size : https://developer.mozilla.org/ko/docs/Web/CSS/font-size

font-weight : https://developer.mozilla.org/ko/docs/Web/CSS/font-weight

color : https://developer.mozilla.org/ko/docs/Web/CSS/color

text-emphasis : https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis

overflow-wrap : https://developer.mozilla.org/ko/docs/Web/CSS/overflow-wrap

text-decoration : https://developer.mozilla.org/ko/docs/Web/CSS/text-decoration

text-aligen: https://developer.mozilla.org/ko/docs/Web/CSS/text-align

