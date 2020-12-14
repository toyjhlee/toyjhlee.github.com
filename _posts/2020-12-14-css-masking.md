---
tags: ['clip', 'clip-path', 'mask']
---

### CSS Masking

시각적 요소의 일부 또는 전체를 숨기기위한 마스킹 및 클리핑을 포함한 수단을 정의하는 CSS 모듈입니다.

-   [203 Tests CSS Masking Module Level 1](https://drafts.fxtf.org/css-masking-1/#mask-borders)
-   [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)
    -   [codepen example](https://codepen.io/yoksel/embed/fsdbu?height=1500&theme-id=1&slug-hash=fsdbu&default-tab=result&user=yoksel&name=cp_embed_8)
        -   browser support

#### CSS속성 Clipping과 Masking 차이점과 특징

[CSS속성 Clipping과 Masking 차이점과 특징](https://shlee1353.github.io/2019/07/15/css-clip-mask/)

#### clip

clip 속성은 현재 deprecated 되었으며, 새로운 속성이 추가되어 더 이상 추천하지 않습니다. 또한, clip은 쉽게 사용하기 어려운 두 가지 제약이 있습니다.

-   [mozilla clip](https://developer.mozilla.org/ko/docs/Web/CSS/clip)

-   엘리먼트에 absolute 속성이 적용되어야 합니다.
-   직사각형 형태로만 적용 가능합니다.

#### clip-path

-   [mozilla clip-path](https://developer.mozilla.org/ko/docs/Web/CSS/clip-path)

```
.clip-circle {
  clip-path: circle(40px at center);
}
```

#### mark

-   [mozilla mark](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
    -   [caniuse](https://caniuse.com/?search=mask)
