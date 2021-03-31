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
