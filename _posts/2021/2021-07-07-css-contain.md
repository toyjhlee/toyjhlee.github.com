---
title: 'Css contain'
---

## 문서

### [mozilla](https://developer.mozilla.org/ko/docs/Web/CSS/contain)

none

-   아무것도 격리하지 않고 요소를 평범하게 렌더링합니다.

strict

-   style을 제외한 모든 격리 규칙을 적용합니다. contain: size layout paint와 같습니다.

content

-   size와 style을 제외한 모든 격리 규칙을 적용합니다. contain: layout paint와 같습니다.

size

-   요소의 크기를 계산할 때 자손의 크기는 고려하지 않아도 됨을 나타냅니다.

layout

-   요소 외부의 어느 것도 내부 레이아웃에 영향을 주지 않고, 그 반대도 성립함을 나타냅니다.

style

-   요소 자신과 자손 외에도 영향을 주는 속성이라도 그 영향 범위가 자신을 벗어나지 않음을 나타냅니다. 이 값은명세에서 "제외 고려" 대상이므로 모든 브라우저가 지원하지 않을 수도 있음을 참고하세요.

paint

-   요소의 자손이 자신의 범위 바깥에 그려지지 않음을 나타냅니다. 이 값을 지정한 요소의 경우, 요소가 화면 밖에 위치할 경우 당연히 그 안의 자손도 화면 안에 들어오지 않을 것이므로 브라우저는 그 안의 요소를 고려하지 않아도 됩니다. 그러나 만약 자손이 범위 밖으로 넘칠 경우에는 요소의 테두리 상자에서 잘라냅니다.

## 글들

[Let’s Take a Deep Dive Into the CSS Contain Property](https://css-tricks.com/lets-take-a-deep-dive-into-the-css-contain-property/)
