---
title: 'sass width styled-components'
---

## sass, scss module 와 styled-components 의 우선순위 조정

-   sass 의 css selector 의 우선 순위가 높아서 styled-components 의 style 에 important 를 적용해야 하는 현상이 생겼다
-   이유는 sass module 를 가져오는 style tag 가 styled-components 의 style tag 보다 뒤에 위치해서

방법은 아래를 링크를 참고 했다

수정 전

```css
/* commonStyle.module.scss */
.afterIcon {
    color: red;
}
```

```javascript
/* useFile.tsx */
const Button = styled.button.attrs(() => ({
    className: commonStyle.afterIcon,
}))`
    color: blue;
}
```

적용한 방법

```javascript
/* useFile.tsx */
const Button = styled.button.attrs(() => ({
    className: commonStyle.afterIcon,
}))`
    && { // 이렇게 되면 .enyJHo.enyJHo
        color: blue;
    }
}
```

[Add "How can I override styles with higher specificity?" to FAQ #187](https://github.com/styled-components/styled-components-website/issues/187)

## 여려개의 버튼을 하나의 styledComponentId 로 제어하는 방법

아래 처럼 버튼을 만들면

```javascript
export const BaseButton = styled.button``

const Button1 = styled(BaseButton)``
const Button2 = styled(BaseButton)``
```

아래와 같이 제어 할 수 있다

```javascript
&:hover .${BaseButton.styledComponentId} {}
```
