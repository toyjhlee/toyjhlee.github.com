### styled-components

-   [home](https://styled-components.com/)
-   [styled-components 를 사용하는 8가지 이유 -번역](https://analogcoding.tistory.com/181)
-   [원문](https://blog.logrocket.com/8-reasons-to-use-styled-components-cf3788f0bb4d/)
-   [styled-components - 벨로퍼트와 함께하는 모던 리액트](https://react.vlpt.us/styling/03-styled-components.html)
-   [Styled-components ThemeProvider를 활용한 스타일 환경 구축](https://velog.io/@hoi/Styled-components-ThemeProvider%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-%EC%8A%A4%ED%83%80%EC%9D%BC-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95)

    -   theme 를 사용 크기 간격을 지정한게 인상 깊다

        ```javascript
        const calcRem = size => `${size / 16}rem`

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
