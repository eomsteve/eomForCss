# background 

## background-image

이미지를 배경으로 사용하게 하는 속성이다.

##### attributes

* `none` : 이미지를 배경으로 사용하지 않는다.
* `url` : 이미지의 URL을 입력한다.

왼쪽 위에서 시작해 가로방향과 세로방향으로 해당 요소를 다 채울때까지 반복되어 나온다. 반복 여부는 `background-repeat`  속성으로 정한다.

## background-repeat

##### attributes

* `repeat` : 가로방향, 세로방향으로 반복한다.
* `repeat-x`: 가로방향으로 반복한다.
* `repeat-y`: 세로방향으로 반복한다.
* `no-repeat`: 반복하지않는다.

## backgroud-size

배경이미지의 가로 크기와 세로 크기를 정할 수 있다.

##### attributes

* `auto` : 이미지 크기를 유지한다.
* `length`: 값을 두개 넣으면 첫 번째값이 가로크기 두번째 값이 세로크기로 정해진다. 값을 한개 넣으면 가로크기이며 세로 크기는 원본이미지의 가로 세로 비율에 맞게 자동으로 정해진다.
* `cover`: 배경을 사용하는 요소를 다 채울수 있게 이미지를 확대 또는 축소한다. 가로 세로 비율을 유지한다.
* `contain`: 배경을 사용하는 요소를 벗어나지 않는 최대 크기로 이미지를 확대 또는 축소한다. 가로 세로 비율을 유지한다.

## background-position

배경 이미지의 위치를 정하는 속성이다.

* x position, y position : 가로 위치와 세로 위치를 정한다. 
* 가로 위치 값 : left, center, right, %, lentgh
* 세로 위치 값 : top, center, bottom, %, length

-----

references

https://www.codingfactory.net/10571

https://developer.mozilla.org/en-US/docs/Web/CSS/background-position