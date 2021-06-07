---
title: 'element lazy loading'
---

## 관련 글 들

[[2020.11.29] 웹 성능 최적화를 위한 Image Lazy Loading 기법](https://helloinyong.tistory.com/297)

[IntersectionObserver를 이용한 이미지 동적 로딩 기능 개선](https://tech.lezhin.com/2017/07/13/intersectionobserver-overview)

[Dominant Colors for Lazy-Loading Images](https://manu.ninja/dominant-colors-for-lazy-loading-images/)

-   image 의 색상 가져오기

## Element 속성

지연 로딩 https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading

### video.preload

-   [설명](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-preload)
-   preload = 'none' 시 autoplay='true' 이면 무시 된다

### css content-visibility

-   [설명](https://wit.nts-corp.com/2020/09/11/6223)
    -   화면에 표시될 때까지 렌더링 작업레이아웃 및 페인팅 포함)를 하지 않을 수 있다
    -   `contain-intrinsic-size`: 크기가 지정되지 않은 div가 공간을 차지할 수 있도록 “intrinsic-size”를 가진 자식 요소가 있는 것처럼 배치됩니다. contain-intrinsic-size는 렌더링 된 콘텐츠 대신 placeholder로서 동작합니다.

#### 숨김 스타일 비교

-   display: none: 요소를 숨기고 렌더링 상태를 제거합니다. 즉, 해당 요소를 표시하기 위해서는 새 요소를 렌더링 하는 것만큼 비용이 많이 듭니다.
-   visibility: hidden: 요소를 숨기면서 렌더링 상태는 유지합니다. 이것은 문서에서 요소를 실제로 제거하지 않으며, 여전히 페이지에서 공간을 차지하고 클릭할 수 있는 상태입니다. 또한 숨겨져 있더라도 필요하면 렌더링 상태를 업데이트합니다.
-   반면 content-visibility: hidden은 렌더링 상태를 유지하면서 요소를 숨기는데, 상태를 변경해야 할 일이 생기면 요소가 다시 화면에 표시될 때만 변경합니다.(예로 content-visibility: hidden 속성이 제거되는 경우)

### img.loading iframe.loading

-   [설명](https://developer.mozilla.org/ko/docs/Web/HTML/Element/img#attr-loading)
