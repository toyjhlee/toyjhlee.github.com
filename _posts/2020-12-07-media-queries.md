---
title: 'media queries'
tags: ['media', 'query']
---

## 문서

### [w3 Media Queries Level 4](https://www.w3.org/TR/mediaqueries-4/)

### [mozilla 미디어 쿼리 사용하기](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Media_queries)

#### 미디어 유형

-   미디어 유형은 장치의 일반적인 범주를 나타냅니다. 미디어 유형은 not이나 only 논리연산자를 사용할 때를 제외하면 선택사항이며 지정하지 않으면 all을 사용합니다.

    -   all
        -   모든 장치에 적합합니다.
    -   print
        -   인쇄 결과물 및 출력 미리보기 화면에 표시 중인 문서입니다. (인쇄 미디어 문서를 방문해 print 형식에서 발생 가능한 서식 문제의 정보를 확인해주세요.)
    -   screen
        -   주로 화면이 대상입니다. speech 음성 합성장치 대상입니다.
    -   사용하지 않는 미디어 유형
        -   CSS2.1과 Media Queries 3 모듈은 여러가지 추가 유형(tty, tv, projection, handheld, braille, embossed, aural)을 정의했으나 Media Queries 4에서 제거됐으므로 사용해선 안됩니다. aural은 유사한 유형인 speech로 대체됐습니다.

#### 미디어 특성

-   (display-mode: fullscreen)

#### 논리 연산자

-   and

    -   and 연산자는 다수의 미디어 특성을 조합하여 하나의 미디어 쿼리를 만들 때 사용합니다. 쿼리가 참이려면 모든 구성 특성이 참을 반환해야 합니다. 미디어 특성과 미디어 유형을 같이 사용할 때도 쓰입니다.

-   not

    -   not 연산자는 미디어 쿼리를 부정하여, 쿼리가 거짓일 때만 참을 반환합니다. 쉼표로 구분한 쿼리 목록 중 하나에서 사용한 경우 전체 쿼리가 아닌 해당하는 하나의 쿼리에만 적용됩니다. not 연산자를 사용할 경우 반드시 미디어 유형도 지정해야 합니다.

-   참고: Level 3 모듈에서는 not 키워드를 사용해 단일 미디어 기능을 부정할 수 없으며 전체 쿼리만 부정 가능합니다.

-   only

    -   only 연산자는 전체 쿼리가 일치할 때만 스타일을 적용할 때 사용하며 오래 된 브라우저가 스타일을 잘못 적용하지 못하도록 방지할 때 유용합니다. only를 사용하지 않은 screen and (max-width: 500px) 쿼리를 가정했을 때, 구형 브라우저는 쿼리를 단순히 screen으로만 읽고 뒷부분은 무시한 채 스타일을 적용해버립니다. only 연산자를 사용할 경우 반드시 미디어 유형도 지정해야 합니다.

-   , (쉼표)
    -   쉼표는 다수의 미디어 쿼리를 하나의 규칙으로 조합할 때 사용합니다. 쉼표 목록 내의 쿼리 각각은 나머지와 별개로 취급하므로, 단 하나의 쿼리만 참을 반환해도 규칙 전체가 참이 됩니다. 즉 쉼표는 논리 or 연산자처럼 동작합니다

#### 미디어 유형 특정하기 [link](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Media_queries#%EB%AF%B8%EB%94%94%EC%96%B4_%ED%8A%B9%EC%84%B1)

-   [Level 4 사양 브라우져 지원](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/@media#Browser_compatibility)

`@media print { ... }`

`@media screen, print { ... }`

#### 미디어 기능 특정하기

`@media (max-width: 12450px) { ... }`

`@media (color) { ... }`

`@media speech and (aspect-ratio: 11/5) { ... }`
