# what is CSS?

CSS 란? Cascading Style Sheets 의 약자이다. cascading 은 계단식, 폭포식 이란 뜻이다. 

CSS 는 HTML 로 작성된 문서의 표시 방법을 기술하기 위한 스타일 시트 언어이다. 

정보(html)와 디자인(css) 를 분리하여 관리할 수 있다. 

#### 사용법

1. HTML 안에서 style 속성을 이용하는 방법
2. `<style>` 태그를 통해 HTML 문서 내부에서 이용하는 방법

```
<head>
 <style type="text/css">
     Selector {property: value;}
    ex) h1 {color:red} 
 </style>
</head>
```

3. 별도로 CSS 파일을 분리하여 HTML 문서에 연결하는 방법

```html
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

#### CSS 적용 우선순위

CSS에서는 우선순위가 적용되는데 적용방법의 우선순위는 크게 

외부스타일(10점) < 내부스타일(20점) < 인라인 스타일(1000점) 순서로 작용한다.

1. 속성값 뒤에 !important 를 붙인 속성
2. HTML 에서 style 을 직접 지정한 속성
3. #id로 지정한 속성
4. .class 로 지정한 속성
5. `태그이름` 으로 지정한 속성
6. 상위 객체에 의해 상속된 속성 

같은 우선순위에 있는 경우 부모- 자식 관계가 많은 경우가 우선되며, 모든 설정이 같은 경우 나중에 선언한 것이 우선되어 적용된다.

-----

references

https://developer.mozilla.org/ko/docs/Web/CSS

우선순위 : https://ofcourse.kr/css-course/%EC%A0%81%EC%9A%A9-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84

