### Radiobox:checked + css:not(:checked)

-   [PureCSS Tabs](https://codepen.io/renatorib/pen/rlpfj)
    -   아이디를 Uniq 하게 만들어야 한다. 아래 코드 사용
        ```javascript
        const getId = function (pre: string = '_') {
            return `${pre}_${Math.random().toString(36).substr(2, 9)}`
        }
        ```
