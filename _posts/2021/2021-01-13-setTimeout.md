---
title: 'window.setTimeout'
---

이하 문서에서 필요한 부분을 적었다

[mozilla setTimeout](https://developer.mozilla.org/ko/docs/Web/API/WindowTimers/setTimeout)

## 문법

3번째 이후 부터의 인자는 param 이구나

```javascript
var timeoutID = window.setTimeout(func[, delay, param1, param2, ...]);
var timeoutID = window.setTimeout(code[, delay]);
window.setTimeout(function, milliseconds);
```

> Internet Explorer 9 이하에서는 함수에 추가적인 매개변수들을 전달하는 기능이 동작하지 않습니다. 만약 브라우저에서 이 기능을 사용하고 싶다면, [polyfill](https://developer.mozilla.org/ko/docs/Web/API/WindowTimers/setTimeout#polyfill)을 사용하세요. (Callback arguments를 봐주세요)

### 지정된 것보다 더 오래 지연되는 이유

#### 중첩된 타임아웃이 4ms 이하일 경우

브라우저들은 setTimeout() "clamping"을 구현했습니다: "최소 지연" 한계보다 작은 지연을 가진 setTimeout() 호출은 최소 지연을 사용하도록 강제됩니다.

#### 비활성 탭에서 타임아웃이1000ms에 여러 번 일어날 경우

부하와 배터리 사용양을 줄이기 위해서, 비활성화 탭들에서 타임아웃이 1초에 여러번 일어나지 않도록 "clamping" 됩니다.

#### 타임아웃 지연

"clamping"과 더불어, 타임아웃은 다른 작업들로 인해 바쁜 페이지에서 늦게 실행될 수 있습니다.
