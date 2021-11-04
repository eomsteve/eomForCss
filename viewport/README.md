# vw vh 

vh : viewport height

vw : viewport weight

현재 실행중인 스크린 크기에 맞춰 상대적 크기를 반환한다.

100 vh , 100 vw 가 전체 화면의 기준이 된다. 

> 예를들어 현재 스크린의 크기가  height =100px, width =80 px이라면 1 vh = 1 px / 1 vw = 0.8 px 이 된다.

Viewport 단위는 viewport의 치수를 기준으로 하고 있기 때문에 요소의 폭, 높이, 크기를 viewport에 맞게 설정해야하는 상황에서 매우 편리하다

> 풀스크린의 배경이미지와 섹션

전체 화면으로 표시되는 요소에 배경 이미지를 설정하는 것이 많다. 제품이나 서비스에 대한 개별 섹션이 화면 가득 표시되도록 Web 사이트를 디자인하고 싶은 경우에 각 요쇼의 폭을 100% width,  높이를 100 vh로 설정하여 만들 수 있다.

## vmin, vmax

* viewport minimum (vmin) :  viewport의 높이와 너비중 작은쪽 치수에 기초로 한다. viewport의 높이가 폭보다 큰 경우, 1 vmin은 viewport의 높이의 1% 에 해당한다. 

- Viewport Maximum (vmax) : viewport의 (높이와 너비 중) 큰 쪽의 치수에 기초로한다. viewport의 높이가 폭보다 큰 경우, 1 vmax는 viewport의 높이의 1%에 해당한다. 

## %와의 차이

100% 기준 100 vw 100 vh 의 차이점은 스크롤바가 발생했느냐 아니냐의 차이이다. 스크롤바가 발생한 이유는 viewport가 스크롤바의 영역을 포함하기 때문이다. 

vw , vh 는 화면 전체 넓이이고, %는 부모의 범위안에서 비율이다. 

-------

references 

https://programming119.tistory.com/93

https://taimouse.tistory.com/8