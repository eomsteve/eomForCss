# Margin collapsing

마진 겹침 혹은 마진 상쇄라 불린다. 마진이 겹치면 상쇄가 일어나게 되는데 이 현상을 마진 겹침 혹은 마진 상쇄라 부른다.

마진 겹침은 세가지 기본 상황에 발생한다. 

1. 인접 형제 : 인접 형제 요소간의 바깥 여백은 서로 상쇄된다.

![](https://media.vlpt.us/post-images/raram2/a4ad2c00-121f-11ea-aaba-65695302c179/01-margin-collapsing-sibling-case.png)

2. 부모와 자식  : 자식, 부모 어느 한 쪽의 박스에 마진을 제외한 박스모델의 구성요소가 아무것도 존재하지 않을때 마진 겹침 현상이 일어난다.(아래 위로만 발생, 좌우로는 발생하지 않는다.)

![](https://media.vlpt.us/post-images/raram2/3bc26dc0-1221-11ea-aaba-65695302c179/03-margin-collapsing-firstchild-case1.png)

부모와 첫 번째(마지막) 자식 사이에 인라인 콘텐츠가 없거나, 상단 하단에 명시적으로 padding, border값을 주지 않았다면 마진이 겹치게 된다. 이때 자식 요소의 마진이 더 크든 작든 상관없이 상쇄된 마진은 부모 박스의 바깥으로만 렌더링이 된다.

3. 빈 블록 : 빈 블럭의 경우 크기가 큰 마진을 선택하여 하나의 마진만 선택한다. 

![](https://media.vlpt.us/post-images/raram2/ffac75c0-121f-11ea-aaba-65695302c179/02-margin-collapsing-emptybox-case.png)

**'빈 요소'** 란 높이(height)가 0인 상태의 블록 요소를 말한다.

- height / min-height / padding / border 등 상하로 늘어나는 프로퍼티 값을 명시적으로 주지 않았거나
- 내부에 Inline 콘텐츠가 존재하지 않는 요소

이 경우 위와 아래를 가르는 **경계**가 없으므로, 자신의 상단 마진의 값과 하단 마진의 값을 비교해 더 큰 값으로 상쇄한다. 만약 겹쳐진 두 값이 동일할 경우, 중복을 상쇄한다. 특히 빈 요소와 인접 박스들 간에 마진 겹침이 일어나는 구조에서는 다음과 같이 상쇄가 여러 번 발생하게 된다.

# 마진 겹침 규칙 적용

마진 겹침은 인접한 두 박스가 온전한 block 요소일 경우에 적용된다.

마진 값이 0이더라도 겹침 규칙은 적용된다.

좌우 마진은 겹치더라도 상쇄되지 않는다.

-----

references

https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing

https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4

https://choicepace.tistory.com/29