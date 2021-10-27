# 브라우저 기본 스타일 

같은 페이지인데도 오페라, 크롬, 사파리, 엣지에서 보이는 모습이 다른 경우가 있다. 특히 모바일에서는 다른 모습이 두드러지게 나타난다. 이는 별도의 스타일을 지정하지 않으면 브라우저에서 제공하는 스타일을 기본값으로 사용하기 때문이다. 

* css reset : 브라우저가 지정한 모든 스타일을 지운다.
* normalize.css : 지정 스타일을 통일한다.

## CSS RESET

스타일 초기화. 모든 속성을 지우고 스킨이 지정한 스타일만 보여준다. 파일의 크기가 작다는 장점이 있으나 모든 스타일을 다시 설정해야한다.

> ```css
> html,body,div,span,applet,object,iframe,h1,h2,h3,h4,h5,h6,p,blockquote,pre,a,abbr,acronym,address,big,cite,code,del,dfn,em,img,ins,kbd,q,s,samp,
> small,strike,strong,sub,sup,tt,var,b,u,i,center,dl,dt,dd,ol,ul,li,fieldset,form,label,legend,table,caption,tbody,tfoot,thead,tr,th,td,article,
> aside,canvas,details,embed,figure,figcaption,footer,header,hgroup,menu,
> nav,output,ruby,section,summary,time,mark,audio,video {
>   margin: 0;
>   padding: 0;
>   border: 0;
>   font-size: 100%;
>   font: inherit;
>   vertical-align: baseline;
> }
> /* HTML5 display-role reset for older browsers */
> article,aside,details,figcaption,figure,footer,header,hgroup,menu,
> nav,section {
>   display: block;
> }
> body {
>   line-height: 1;
> }
> ol,
> ul {
>   list-style: none;
> }
> blockquote,
> q {
>   quotes: none;
> }
> blockquote:before,
> blockquote:after,
> q:before,
> q:after {
>   content: "";
>   content: none;
> }
> table {
>   border-collapse: collapse;
>   border-spacing: 0;
> }
> input:focus {
>   outline: none;
> }
> a {
>   color: inherit;
>   text-decoration: none;
> }
> ```

* https://meyerweb.com/eric/tools/css/reset/index.html

## normalize.css 

모든 브라우저에서 표준 스타일을 보연준다. 스타일을 바닥부터 재 정의하지 않아도 된다는 장점이 있으나 파일의 크기가 크다. `<head></head>` 안에 스크립트를 추가하여 사용한다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css" />
  </head>
  <body></body>
</html>
```

* https://cdnjs.com/libraries/normalize

### 적용후

![image-20210905030058004](C:\Users\mingy\AppData\Roaming\Typora\typora-user-images\image-20210905030058004.png)

-----

references

http://designbase.co.kr/webcoding-10/

https://meyerweb.com/eric/tools/css/reset/index.html

https://velog.io/@jewon119/01.CSS-%EA%B8%B0%EC%B4%88-Reset-CSS