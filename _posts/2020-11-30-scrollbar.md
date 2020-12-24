---
title: 'scrollbar'
tags: ['utils', 'detection']
---

## utils

### Cross-Browser JavaScript Scrollbar Detection

-   대부분의 브라우저에서 작동

    -   IE9 +, 자동으로 숨겨지는 Mac의 Chrome 에서도 작동

        -   이유는 : window.innerWidth 가 IE8 에는 없다

    -   `const hasScrollbar = window.innerWidth > document.documentElement.clientWidth`

    -   IE8을 지원하지 않으니 에러가 발생하는 것을 막기 위해 아래와 같이 수정
    -   ```
        let hasScrollbar = false
        if (document.documentElement) { hasScrollbar = window.innerWidth > document.documentElement.clientWidth }
        ```

-   [link](https://tylercipriani.com/blog/2014/07/12/crossbrowser-javascript-scrollbar-detection/)

### get Scrollbar Width

-   [출처](https://stackoverflow.com/questions/13382516/getting-scroll-bar-width-using-javascript#answer-13382873)

    ```javascript
    function getScrollbarWidth() {
        // Creating invisible container
        const outer = document.createElement('div')
        outer.style.visibility = 'hidden'
        outer.style.overflow = 'scroll' // forcing scrollbar to appear
        outer.style.msOverflowStyle = 'scrollbar' // needed for WinJS apps
        document.body.appendChild(outer)

        // Creating inner element and placing it in the container
        const inner = document.createElement('div')
        outer.appendChild(inner)

        // Calculating difference between container's full width and the child width
        const scrollbarWidth = outer.offsetWidth - inner.offsetWidth

        // Removing temporary elements from the DOM
        outer.parentNode.removeChild(outer)

        return scrollbarWidth
    }
    ```
