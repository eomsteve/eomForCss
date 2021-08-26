# CSS with div tag 

div 태그는 HTML 문서에서 특정 영역(division) 이나, 구획(section)을 정의할때 사용한다.

div 태그 요소는 여러 HTML  요소들을 하나로 묶어주어 CSS로 스타일을 변경하거나 자바 스크립트로 특정 작업을 수행하기 위한 일종의 컨테이너로 자주 사용된다. 

웹 페이지의 레이아웃을 설정하는데 종종 사용된다. 

CSS로 꾸미기 전에는 콘텐츠나 레이아웃에 어떤영향도 주지 않는다.

* div tag 는 블록 레벨 태그이다.
* 일반 컨태이너 테그이다.

#### div tag width, height

div tag는 width 와 height로 너비와 높이를 설정할 수 있다. 가장 대표적인 방법으론 px값을 명시하는 방법이 있다. 요즘은 다양한 화면의 크기를 대응하기 위해 rem,em,%등을 사용하기도 한다.

## HTML 부모와 자식

html 요소는 박스로 이루어져 있으며 다른 요소들의 내부에 배치될 수도 있고 다른 요소들과 나란히 배치될 수도 있다.

**부모** **자식** : html 요소간에는 부모, 자식 관계가 형성되는데 이런 관계는 상대적이다. 예를 들면 부모는 포함하는 태그, 자식은 포함되는 태그를 말한다. html 최상위 태그는 `<html>` 태그이다. 이 html 태그는 최상위 태그이므로 모든 태그의 부모 태그가 된다.

부모 자식관계를 통해 속성값의 상속이 가능하다. 속성값은 부모로부터 자식으로 전파된다. 

#### 자식 태그에서 %로 크기 설정

자식 태그에서 %로 크기를 설정하게 되면 부모의 크기에 비례하여 크기가 결정된다. 

예를 들어 가로 길이가 300px , 세로 길이가 100px인 태그 안에 자식 태그를 width = 50%, height = 50%로 설정하게 된다면 가로 길이가 150px, 세로 길이가 50px인 요소가 부모 태그 안에 생성이 된다. 

-----

references

http://tcpschool.com/html-tags/div

https://developer.mozilla.org/ko/docs/Web/HTML/Element/div

https://coding-factory.tistory.com/188

부모자식:

https://thrillfighter.tistory.com/470