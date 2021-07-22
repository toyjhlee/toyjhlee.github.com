---
title: 'styled-components'
---

## 문서

[home](https://styled-components.com/)

## 소계 글

[styled-components 를 사용하는 8가지 이유 -번역](https://analogcoding.tistory.com/181)

[원문](https://blog.logrocket.com/8-reasons-to-use-styled-components-cf3788f0bb4d/)

[styled-components - 벨로퍼트와 함께하는 모던 리액트](https://react.vlpt.us/styling/03-styled-components.html)

## Example

[Styled-components ThemeProvider를 활용한 스타일 환경 구축](https://velog.io/@hoi/Styled-components-ThemeProvider%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-%EC%8A%A4%ED%83%80%EC%9D%BC-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95)

-   theme 를 사용 크기 간격을 지정한게 인상 깊다

```javascript
const calcRem = size => `${size / 16}rem`
```

```javascript
const fontSizes = {
    small: calcRem(14),
    base: calcRem(16),
    lg: calcRem(18),
    xl: calcRem(20),
    xxl: calcRem(22),
    xxxl: calcRem(24),
    titleSize: calcRem(50),
}

const deviceSizes = {
    mobileS: '320px',
    mobileM: '375px',
    mobileL: '450px',
    tablet: '768px',
    tabletL: '1024px',
}
```

## blog

[medium.com](https://medium.com/styled-components)

### [How styled-components works: A deep dive under the hood](https://medium.com/styled-components/how-styled-components-works-618a69970421)

use styled-components v3.3.3

#### BaseStyledComponent

1. Evaluating tagged template
2. Generating CSS class name. CSS 클래스 이름 생성 : [MurmurHash](https://www.wikiwand.com/en/MurmurHash) 알고리즘
3. CSS Preprocessing. CSS 전처리 : [stylis CSS preprocessor](https://github.com/thysultan/stylis.js)
4. Injecting CSS string into the page

#### styled-components renders an element with 3 class names:

1. this.props.className
2. componentId
3. generatedClassName

#### Performance tips

## API

```
const Div = styled.div``
Div.styledComponentId // sc-fzoJus
```

## utils

### get css. css 가져오기

```
const Div = styled.div``

let result = []
Div.componentStyle?.rules.forEach((expr, index) => {
    const isFunc = typeof expr === 'function'
    const value = isFunc ? expr(props) : expr

    result.push(value)
})

```

[CSS-in-JS에서 CSS-in-CSS로 바꿔야 하는 이유](https://blueshw.github.io/2020/09/14/why-css-in-css/)

[CSS-in-JS(Styled Components) vs CSS-inCSS(CSS Modules) 성능 비교](https://blueshw.github.io/2020/09/27/css-in-js-vs-css-modules/)

## styled-component vs emotion

### state of css

[link](https://2020.stateofcss.com/ko-KR/technologies/css-in-js)

### styled-components-vs-emotion

[link](https://github.com/jsjoeio/styled-components-vs-emotion)

-   시간이 지남에 따라 두 API 는 비슷해졌다

### Emotion vs Styled Components

2019.12.18 ~ 2019.12.24

[link](https://spectrum.chat/styled-components/general/emotion-vs-styled-components~706ff9c8-f06d-4433-a42c-cc158d385089)

-   styled-component 가 생태계와 인기 있다는 이유로 추천

### stackshare

[link](https://stackshare.io/stackups/emotion-vs-styled-components)

-   styled-component 가 투표를 더 받음

### Styled-components vs. Emotion for handling CSS

2021.01.21

[link](https://blog.logrocket.com/styled-components-vs-emotion-for-handling-css/)

간단한 스타일 emotion

독특하고 복잡한 스타일 -> styled-component

### A Thorough Analysis of CSS-in-JS

[link](https://css-tricks.com/a-thorough-analysis-of-css-in-js/)

### 사용법

How To Use Emotion for Styling in React

[link](https://www.digitalocean.com/community/tutorials/react-react-emotion)
