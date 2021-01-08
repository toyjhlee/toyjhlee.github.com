---
title: 'html issue'
---

> 여긴 html 에서 생각과 다르게 동작하는 사례과 해결책을 모아 둔다

## `Warning: Received 'true' for a non-boolean attribute 'loading'. If you want to write it to the DOM, pass a string instead: loading="true" or loading={value.toString()}.`

-   `Button` 를 styled-components 로 만들어 loading 이라는 property 를 가지게 한 상황에서 나오는 Warning
-   loading 을 다른 단어로 변경하면 Warning 이 발생하지 않는다
-   img 테크에는 loading 이라는게 사용되는데.. 이래서 그런가? [HTMLImageElement.loading](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/loading)
