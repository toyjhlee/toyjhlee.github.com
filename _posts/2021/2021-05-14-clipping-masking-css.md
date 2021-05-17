---
title: 'Clipping and Masking in CSS with IE'
---

image clip, mask

[mask-image](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image) [clip-path](https://developer.mozilla.org/ko/docs/Web/CSS/clip-path)

-   요소의 특정 부분만 나오도록 할 수 있습니다.

결론 IE11 를 지원를 위해서는 SVG mark 를 이용하는 방법이 좋을 듯 합니다

[svg 의 mark 를 이용하는 방법](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask)

CSS clip-path 이용하는 방법 중 IE11 를 지원하는 방법은 찾지 못 했습니다. canvas 를 이용하는 방법은 하나 있습니다

[clip-path IE 지원 안 됨](https://caniuse.com/?search=clip-path)

참고로 제가 찾은 clip-path 폴리필은 아래와 같습니다

1. CSS-Filters-Polyfill -> https://github.com/Schepp/CSS-Filters-Polyfill IE 는 6~9 까지 지원 IE 11 는 지원하지 않음

2. canvas 를 이용 lib https://github.com/StasGlebov/Clip-path-polyfill)
