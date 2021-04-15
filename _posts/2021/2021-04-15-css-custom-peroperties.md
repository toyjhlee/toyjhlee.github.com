---
title: 'css custom properties'
---

## 설명

사용자 지정 속성(CSS 변수, 종속 변수)은 CSS 저작자가 정의하는 개체로, 문서 전반적으로 재사용할 임의의 값을 담습니다. 사용자 지정 속성은 전용 표기법을 사용해 정의하고, (--main-color: black;) var() 함수를 사용해 접근할 수 있습니다. (color: var(--main-color);)

## 사용법

```css
element {
    --main-bg-color: brown;
}
```

```css
:root {
    --main-bg-color: brown;
}
```

### :root

CSS :root 의사 클래스는 문서 트리의 루트 요소를 선택합니다 HTML의 루트 요소는 <html> 요소이므로, :root의 명시도가 더 낮다는 점을 제외하면 html 선택자와 똑같습니다. [참고](https://developer.mozilla.org/ko/docs/Web/CSS/:root)

### 유효하지 않은 변수 처리

```scss
.gray {
    color: var(--gray, #dcdcdc);
}
```

## 알게 된 점

### property 가 두번 선언되는 이유 방어 코드

```scss
.gray {
    color: #dcdcdc;
    color: var(--gray);
}
```

## test

[다음을 참고](/front-test/#testing-sass-with-jest)

## 참고

-   [:root 가상선택자와 CSS 변수](https://blog.thereis.xyz/136)
-   [사용자 지정 CSS 속성 사용하기](https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties)
