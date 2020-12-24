---
title: 'css background'
---

## 문서

### background-clip [mozilla](https://developer.mozilla.org/ko/docs/Web/CSS/background-clip)

-   CSS background-clip 속성은 요소의 배경이 테두리, 안쪽 여백, 콘텐츠 상자 중 어디까지 차지할 지 지정합니다.
-   IE9+, text : not IE [caniuse](https://caniuse.com/?search=background-clip)
    -   border-box
        -   배경이 테두리의 바깥 경계까지 차지합니다. (Z축 순서 상 테두리 아래 위치)
    -   padding-box
        -   배경이 안쪽 여백의 바깥 경계까지 차지합니다. 테두리 밑에는 배경을 그리지 않습니다.
    -   content-box
        -   배경을 콘텐츠 상자에 맞춰 그립니다.
    -   text
        -   배경을 전경 텍스트 위에만 그립니다.

### background-origin [mozilla](https://developer.mozilla.org/ko/docs/Web/CSS/background-origin)

-   CSS background-origin 속성은 배경의 원점을 테두리 시작점, 테두리 내부, 안쪽 여백 내부 중 하나로 지정합니다.
-   IE9+ [caniuse](https://caniuse.com/?search=background-origin)
    -   border-box
        -   배경을 테두리 박스에 상대적으로 배치합니다.
    -   padding-box
        -   배경을 안쪽 여백 박스에 상대적으로 배치합니다.
    -   content-box
        -   배경을 콘텐츠 박스에 상대적으로 배치합니다.
