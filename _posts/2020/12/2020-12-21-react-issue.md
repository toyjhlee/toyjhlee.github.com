---
title: 'react issue'
tags: ['react', 'issue', 'scrollTop']
---

> 개발 시 문제가 생긴 것을 적는다

## `Warning: Can't perform a React state update on an unmounted component. This is a no-op, but it indicates a memory leak in your application. To fix, cancel all subscriptions and asynchronous tasks in a useEffect cleanup function. typescript`

-   해결 [Solve React useEffect Memory Leak Cancel Subscriptions Cleanup Function](https://sunilrk.medium.com/solve-react-useeffect-memory-leak-cancel-subscriptions-cleanup-function-2ef100b9dc9)

## React hook 에서 두 번 render 되는 현상

[React Hooks render twice](https://stackoverflow.com/questions/58603209/react-hooks-render-twice)

It's an intentional feature of the StrictMode. This only happens in development, and helps find accidental side effects put into the render phase. We only do this for components with Hooks because those are more likely to accidentally have side effects in the wrong place. -- [gaearon commented on Mar 9, 2019](https://github.com/facebook/react/issues/15074)

## react-router scroll to top

아래 방법은 react-router 환경에서 scrollTo 가 원하는 대로 되지 않았다 `scrollRestoration = 'manual'` 할당해도 같았다.

```jsx
useEffect(() => {
    window.scrollTo(0, 0)
}, [history.location.pathname])
```

### 해결 방법

다른 방법1, 다른 방법2를 합쳐서 해결했다

```jsx
import {useEffect} from 'react'
import {withRouter} from 'react-router-dom'

function ScrollToTop({history}) {
    if (window.history.scrollRestoration === 'auto') {
        window.history.scrollRestoration = 'manual'
    }

    useEffect(() => {
        const unlisten = history.listen(() => {
            window.scrollTo(0, 0)
        })
        return () => {
            unlisten()
        }
    }, [])

    return null
}

export default withRouter(ScrollToTop)
```

### 다른 방법 1

[react-router scroll to top on every transition](https://stackoverflow.com/questions/36904185/react-router-scroll-to-top-on-every-transition#answer-54343182)

```jsx
import {useEffect} from 'react'
import {withRouter} from 'react-router-dom'

function ScrollToTop({history}) {
    useEffect(() => {
        const unlisten = history.listen(() => {
            window.scrollTo(0, 0)
        })
        return () => {
            unlisten()
        }
    }, [])

    return null
}

export default withRouter(ScrollToTop)
```

### 다른 방법 2

> react-router 에서는 적용되지 않는 걸로 확인 되었다

scrollRestoration 을 비활성화

```javascript
if (history.scrollRestoration) {
    window.history.scrollRestoration = 'manual'
}
```

-->

## act warning

React.act 로 감싸는 것으로 해결 되지 않는 경우가 있었다. 아래 글을 보고 해결했다. act 관련 경우들의 해결 방법을 설명하고 있다

[Fix the "not wrapped in act(...)" warning](https://kentcdodds.com/blog/fix-the-not-wrapped-in-act-warning#an-alternative-waiting-for-the-mocked-promise)

[관련 영상](https://egghead.io/lessons/jest-fix-the-not-wrapped-in-act-warning)

```typescript
const promise = Promise.resolve()
```

## for more information. Args: .sc-bBXqnf

### 에러 메시지

-   `Cannot create styled-component for component: .sc-bBXqnf`
-   `prettier-plugin-sort-imports` 을 적용하면 서 React import 가 polyfill 위로 가면서 생긴 현상
-   `개체가 'repeat' 속성이나 메서드를 지원하지 않습니다`

### before

```es6
import React from 'react'
import 'react-app-polyfill/ie11'
import 'react-app-polyfill/stable'
```

### after

```es6
import 'react-app-polyfill/ie11'
import 'react-app-polyfill/stable'

import React from 'react'
```
