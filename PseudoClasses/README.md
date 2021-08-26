# 가상 클래스 선택자

보통 선택자는 HTML 태그, 클래스, ID등 HTML 요소를 직접적으로 선택하여 CSS를 꾸며준다. 

CSS에는 가상요소와 가상 클래스가 있다. 이것들을 사용해서 html 문서의 수정없이 CSS만으로 디자인적 요소를 추가할 수 있다. html 요소를 직접적으로 선택하지 않고, 요소의 상태에 따라 선택하여 꾸며주는것을 의미한다. 

* checked : 라디오, 체크박스가 선택됨을 나타낸다. 사용자가 채크했거나 선택한 경우 활성화 되고, 해제하는 경우 비활성화 된다.
  * `input[type="checkbox"]:checked`
* visited : 방문한 적이 있는 링크를 선택한다.
  * `a:visited` 
* link : 방문하지 않은 링크를 선택한다. 대부분의 브라우저는 링크에 기본값으로 색상을 지정한다. 따라서 링크를 방문한적이 없을 경우 글자 색이 적용된 모습을 볼 수 있다.
  * `a:link`
* hover : 마우스를 위에 올린 상태, 마우스가 해당 요소 위에 있을때 스타일을 변경할 수 있다.
  * `div:hover`
* active :  마우스로 클릭한 상태, 마우스가 해당 요소를 클릭하는 순간부터 떼는 순간까지 요소의 스타일을 변경할 수 있다.
  * `div:active`

-----

references

https://bio-info.tistory.com/67

https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes

