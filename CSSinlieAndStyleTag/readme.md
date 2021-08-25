# HTML in-line style and style tag

### CSS 적용 방법 3가지

1. 인라인 스타일 : 한 줄짜리 스타일, 태그에 직접 지정하여 사용한다. 이러한 인라인 스타일은 해당 요소에만 스타일을 적용할 수 있습니다.

   ```html
   <div style="color:red;"></div>
   ```

   

2. 내부 스타일시트(style tag) : 내부 스타일시트를 이용하는 방법은 HTML 문서내에 `<head>` 태그를 사용하여 CSS 스타일을 적용한다.

   이러한 내부 스타일 시트는 해당 HTML 문서에만 스타일을 적용할 수 있다.

   ```html
   <head>
       <style>
           div {
               background-color:red;
           }
       </style>
   </head>
   ```

   

3.   외부 스타일 시트: 외부 스타일시트를 이용하는 방법은 웹 사이트 전체의 스타일을 하나의 파일에서 변경할 수 있도록 해준다. 

   외부에서 작성된 스타일시트 파일은 확장자가 .css 이다.

   스타일을 적용할때 `<head>` 태그에 `<link>` 태그를 사용하여 외부 스타일 시트를 포함해야만 스타일이 적용된다.

   ```html
   <head>
   
       <link rel="stylesheet" href="/examples/media/expand_style.css">
   
   </head>
   ```

## 스타일의 적용 순위

CSS에서는 우선순위가 적용되는데 적용방법의 우선순위는 크게 

외부스타일(10점) < 내부스타일(20점) < 인라인 스타일(1000점) 순서로 작용한다.

1. 속성값 뒤에 !important 를 붙인 속성
2. HTML 에서 style 을 직접 지정한 속성
3. #id로 지정한 속성
4. .class 로 지정한 속성
5. `태그이름` 으로 지정한 속성
6. 상위 객체에 의해 상속된 속성 

같은 우선순위에 있는 경우 부모- 자식 관계가 많은 경우가 우선되며, 모든 설정이 같은 경우 나중에 선언한 것이 우선되어 적용된다.

# color attributes

CSS color 자료형은 sRGB 색 공간의 한 색을 표현하며, 추가로 알파채널 투명도 값도 가질 수 있다. 

### 사용법

* `red`, `blue`등 이미 정의된 색
* `#000`, `#FFFFFF` 등의 16진수 색상 코드
* `rgb(255, 255, 255)` 등의 rgb 색상
* `rgba(200, 100, 150, 0.5)` 등의 알파(투명도)가 적용된 rgba 색상

```css
div{
    color : red;
}
div2{
   color: #0A0; 
}
div3{
    color: rgb(0, 0, 150);
}
div4{
    color: rgba(30, 150, 100, 0.5);
}
```



-----

references

inline : http://tcpschool.com/css/css_intro_apply

color 

* https://ofcourse.kr/css-course/color-%EC%86%8D%EC%84%B1

* https://developer.mozilla.org/ko/docs/Web/CSS/color_value





