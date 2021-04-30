---
title: 'React Typography'
---

## 설명

Typography Component 를 만들면서 참고한 글들을 적어본다

## property 와 sass className 연결

### [An Introduction to Reusable Components and how to create Typography Component](https://dev.to/nghiemthu/an-introduction-about-reusable-components-and-creating-typography-component-4c6o)

```scss
.typography--variant-h1 {
    font-size: 6rem;
    font-weight: 500;
}

.typography--variant-h2 {
    font-size: 3.75rem;
    font-weight: 500;
}
```

```typescript
const Button = ({color, children, ...props}) => {
    return (
        <button
            className={cn({
                'button--color-primary': color === 'primary',
            })}
            {...props}
        >
            {children}
        </button>
    )
}
```

## Dynamic tag

### [Typing a dynamic tag in React with TypeScript?](https://stackoverflow.com/questions/55969769/typing-a-dynamic-tag-in-react-with-typescript)

a tag 외는 타입을 더 지정해 주어야 하는 방법

tag 자동완성을 위해 여기에 `ComponentType` 을 추가했다. 아래와 같다

```typescript
import {ComponentType} from 'react'
interface CompProps {
    tag: ComponentType keyof JSX.IntrinsicElements
}

const MyComponent: React.FunctionComponent<CompProps & React.HTMLAttributes<HTMLOrSVGElement>> = ({tag: Wrapper = 'div', children, ...rest}) => {
    return <Wrapper {...rest}>{children}</Wrapper>
}
```

## 그외 참고하면 좋을 방법들

### [Building a React typography system](https://levelup.gitconnected.com/building-a-react-typography-system-f9d1c8e16d55)

[codesandbox](https://codesandbox.io/s/kw89ro5y2r?file=/src/DynamicComponent/index.js)

`clean-tag`,`styled-system`, `styled-components` 을 사용아여 구축하고 있다.

#### styled-system 샘플 코드

```typescript
import styled from 'styled-components'
import { space, layout, typography, color } from 'styled-system'

const Box = styled.div`
  ${space}
  ${layout}
  ${typography}
  ${color}
`

<Box width={1/2} />
```

## 참고
