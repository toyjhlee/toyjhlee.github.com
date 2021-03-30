---
title: 'IE 를 지원하지 않는다면'
---

## 참고 사이트

[caniuse/](https://caniuse.com/)

[QuirksMode.org - CSS](https://www.quirksmode.org/css/)

## 필요한 것 들

[사용자 지정 CSS 속성 사용하기 (변수)](https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties)

[inline-size](https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size)

[MediaDevices.getUserMedia()](https://developer.mozilla.org/ko/docs/Web/API/MediaDevices/getUserMedia)

[CSS 그리드 레이아웃](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Grid_Layout)

[cursor cur, ani 포맷](https://developer.mozilla.org/ko/docs/Web/CSS/cursor/Using_URL_values_for_the_cursor_property)

-   [참조](/cursor)

[position: sticky](https://developer.mozilla.org/ko/docs/Web/CSS/position)

[background-clip](https://developer.mozilla.org/ko/docs/Web/CSS/background-clip)

[env](https://developer.mozilla.org/en-US/docs/Web/CSS/env)

<!-- [box-decoration-break](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break) -->

-   [참조](/css-background)

[참조 css-issue](/css-issue)

[::placeholder](https://developer.mozilla.org/ko/docs/Web/CSS/::placeholder)

-   아래 방법으로 사용 가능

```
:-ms-input-placeholde {}
```

[backdrop-filter](https://developer.mozilla.org/ko/docs/Web/CSS/backdrop-filter)

> 요소 뒤 영역에 흐림이나 색상 시프트 등 그래픽 효과를 적용할 수 있는 속성입니다. 요소 "뒤"에 적용하기 때문에, 효과를 확인하려면 요소나 요소의 배경을 적어도 반투명하게는 설정해야 합니다.

-   [codepen](https://codepen.io/robinrendle/pen/LmzLEL)

[picture](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)

-   예시 blog [Built-in Browser Support for Responsive Images](https://www.html5rocks.com/ko/tutorials/responsive/picture-element/)
-   [mozilla 반응형 이미지](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

[img.srcset](https://developer.mozilla.org/ko/docs/Web/HTML/Element/img)

```jsx
<img src="/files/16864/clock-demo-200px.png"
     alt="Clock"
     srcset="/files/16864/clock-demo-200px.png 200w,
             /files/16797/clock-demo-400px.png 400w"
     sizes="(max-width: 600px) 200px, 50vw">
```

[filter](https://developer.mozilla.org/ko/docs/Web/CSS/filter)

-   CSS filter 속성은 흐림 효과나 색상 변형 등 그래픽 효과를 요소에 적용합니다. 보통 필터는 이미지, 배경, 테두리 렌더링을 조정하는 데 쓰입니다.

-   CSS 표준은 미리 정의된 효과를 내는 몇 가지 함수를 포함하고 있습니다. SVG 필터 요소를 가리키는 URL 참조를 사용하여 SVG 필터를 적용할 수도 있습니다.

-   필터 함수
    -   url()
    -   blur()
    -   brightness()
    -   contrast()
    -   drop-shadow()
    -   grayscale()
    -   hue-rotate()
    -   invert()
    -   opacity()
    -   saturate()
    -   sepia()
    -   함수 조합 가능

[revert](https://developer.mozilla.org/ko/docs/Web/CSS/revert)

-   revert 는 현재 엘리먼트에 선언 된 캐스캐이딩된 속성으로부터 style origin 으로 되돌립니다
