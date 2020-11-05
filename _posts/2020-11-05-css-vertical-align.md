### hivelab 의 Vertical-align 파헤치기

설명이 잘 되어 있다

-   [[공유] Vertical-align 파헤치기! – 1부](http://blog.hivelab.co.kr/%EA%B3%B5%EC%9C%A0-vertical-align-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-1%EB%B6%80/)

-   [[공유] Vertical-align 파헤치기! – 2부](http://blog.hivelab.co.kr/%ea%b3%b5%ec%9c%a0-vertical-align-%ed%8c%8c%ed%97%a4%ec%b9%98%ea%b8%b0-2%eb%b6%80/)

-   IE 에 box 가 vertical-align center 에 오지 않았다
    -   [해결 링크](https://github.com/philipwalton/flexbugs/issues/231#issuecomment-362790042)
    ```css
    .flex-container {
        min-height: 100px;
        display: flex;
        align-items: center;
    }
    .flex-container:after {
        content: '';
        min-height: inherit;
        font-size: 0;
    }
    ```
