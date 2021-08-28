# CSS BOX

CSS에 포함되는 모든 요소는 박스 모양으로 구성되면 이것을 box model이라고 부른다. 박스 모델은 HTML 요소를 padding, margin, content로 구분한다.

![](http://tcpschool.com/lectures/img_css_boxmodel.png)

1. content : 텍스트나 이미지가 들어있는 박스의 실질적인 내용 부분이다.
2. padding : 내용과 테두리 사이의 간격, 패딩은 눈에 보이지 않는다.
3. border 테두리, 내용과 패딩 주면을 감싸는 테두리이다.
4. margin : 테두리와 이웃하는 요소 사이의 간격이다. 

표준 박스 모델에서 width 와 height를 부여하면 content box의 너비와 높이가 정의된다. 그런 다음 패딩과 테두리는 박스의 너비와 높이에 추가되여 박스가점유하는 전체 크기가 정해진다.

```css
.box {
  width: 350px;
  height: 150px;
  margin: 25px;
  padding: 25px;
  border: 5px solid black;
}
```

만약 박스가 위와같이 정의되어 있다면

실제로 너비는 (350 + 25 + 25 + 5 + 5 : width,양쪽 padding, 양쪽 border) = 410

![](http://tcpschool.com/lectures/img_css_boxsize.png)

**참고**: 마진은 박스의 실제 크기에 포함되지 않는다. 물론 여백은 박스가 페이지에서 차지하는 총 공간에 영향을 미치지만, 박스의 외부 공간에만 영향을 미친다. 박스의 영역은 테두리에서 멈추게 된다. 여백으로 확장 X

## margin padding border

### margin

마진은 박스 주변에 보이지 않는 공간이다. 마진은 박스로부터 다른 요소를 밀어낸다. 마지는 양수값 또는 음수값을 가질 수 있다. 박스 한쪽 측면에 음수값 여백을 설정하면 페이지의 다른부분과 공백이 겹칠수 있다. 

### border

테두리는 박스의 마진과 패딩 사이에 그려진다. 테두리의 크기는 박스의 width와 height에 포함된다. 

### padding

패딩은 테두리와 콘텐츠 영역 사이에 위치한다. 마진과는 다르게 패딩은 음수의 크기를 가질 숭벗어 그값은 0또는 양수 값이여야 한다.

# box-sizing

box-sizing은 박스의 크기를  어떤 기준으로 계산할지 정하는 속성이다.

CSS 박스 모델의 기본값에서, 지정한 여비와 높이는 콘텐트 박스 크기에만 적용된다. 테두리나 패딩이 있으면 너비와 높이는 더 커진다. 따라서 크기를 설정할때 원하는 크기를 얻으려면 테두리나 안쪽 여백을고려해야 한다.

box-sizing 속성을 이용해 방식을 바꿀 수 있다.

* `content-box` 는 기본 CSS 박스 크기 결정법을 사용한다. (content 영역 기준으로 크기를 정함)
* `border-box`는 테두리와 안쪽 여백의 크기도 요소의 크기로 고려한다. (테두리를 기준으로 크기를 정함)

# contents

콘텐츠 영역은 콘텐트 경계가 감싼 영역으로 글이나 이미지 비디오 등 요소의 실제 내용을 포함한다. 콘텐츠 영역의 크기는 콘텐츠 너비와 콘텐츠 높이이다. 

-----

references

https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/The_box_model

http://tcpschool.com/css/css_boxmodel_boxmodel

box sizing : https://developer.mozilla.org/ko/docs/Web/CSS/box-sizing

content : https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model