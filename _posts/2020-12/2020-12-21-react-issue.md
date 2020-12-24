---
title: 'react issue'
tags: ['react', 'issue']
---

> 개발 시 문제가 생긴 것을 적는다

## `Warning: Can't perform a React state update on an unmounted component. This is a no-op, but it indicates a memory leak in your application. To fix, cancel all subscriptions and asynchronous tasks in a useEffect cleanup function. typescript`

-   해결 [Solve React useEffect Memory Leak Cancel Subscriptions Cleanup Function](https://sunilrk.medium.com/solve-react-useeffect-memory-leak-cancel-subscriptions-cleanup-function-2ef100b9dc9)

## React hook 에서 두 번 render 되는 현상

[React Hooks render twice](https://stackoverflow.com/questions/58603209/react-hooks-render-twice)

It's an intentional feature of the StrictMode. This only happens in development, and helps find accidental side effects put into the render phase. We only do this for components with Hooks because those are more likely to accidentally have side effects in the wrong place. -- [gaearon commented on Mar 9, 2019](https://github.com/facebook/react/issues/15074)
