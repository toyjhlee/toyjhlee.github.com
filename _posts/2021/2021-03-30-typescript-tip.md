---
title: 'Typescript Tip'
---

## input component 만들기

### React attribute prop override

참고 : [Typescript React: How to override default html input element attribute prop types](https://stackoverflow.com/questions/64274764/typescript-react-how-to-override-default-html-input-element-attribute-prop-type)

```Typescript
type InputProps = {
    size?: 'sm' | 'md' | 'lg';
} & Omit<A, 'size'>;
```

```Typescript
export type InputProps = {
    type: inputType
    size: inputSize
    onChange: (value: string) => void
} & Omit<InputHTMLAttributes<HTMLInputElement>, 'size' | 'type' | 'onChange'>
```

### 생각

기본 property name 과 겹치지 말자
