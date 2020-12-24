---
title: 'web api console'
tags: ['console']
---

# Web API console

[mozilla](https://developer.mozilla.org/ko/docs/Web/API/Console)

console 객체는 브라우저의 디버깅 콘솔(Firefox 웹 콘솔 등)에 접근할 수 있는 메서드를 제공합니다. 동작 방식은 브라우저마다 다르지만, 사실상 표준으로 여겨지는 기능도 여럿 있습니다.

console 객체는 아무 전역 객체에서나 접근할 수 있습니다. 브라우징 문맥에선 Window, 워커에서는 WorkerGlobalScope이 속성으로 포함하고 있습니다. Window.console의 형태로 노출되어 있으므로 간단하게 console로 참조할 수 있습니다.

> 주의: 이 기능은 Web Worker에서 사용할 수 있습니다.

> 참고: 실제 console 인터페이스는 역사적 이유로 인해 모두 소문자(즉 Console이 아니고 console)입니다.

## 메서드

자세한 것은 [mozilla 참고](https://developer.mozilla.org/ko/docs/Web/API/Console#%EB%A9%94%EC%84%9C%EB%93%9C)

### console.assert()

메서드는 주어진 가정이 거짓인 경우 콘솔에 오류 메시지를 출력합니다. 참인 경우, 아무것도 하지 않습니다.

```
console.assert(assertion, obj1 [, obj2, ..., objN]);
```

### console.clear()

콘솔의 내용을 지웁니다.

> 주의: 이 기능은 Web Worker에서 사용할 수 없습니다

### console.count()

주어진 레이블로 메서드를 호출한 횟수를 출력합니다.

### console.countReset()

주어진 라벨의 횟수를 초기화합니다.

### console.debug()

메서드는 메시지를 "디버그" 중요도로 콘솔에 출력합니다. 디버그 중요도 메시지는 별도 설정 없이는 보이지 않습니다.

### console.dir()

주어진 JavaScript 객체의 속성 목록을 상호작용 가능한 형태로 표시합니다. 속성 값이 다른 객체라면 펼쳐서 살펴볼 수 있습니다.

![console-dir.png](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/3603/678b88d6716cbb4ae59927e8cd8b02d2/console-dir.png)

### console.dirxml()

객체를 XML/HTML 요소 형태로 나타낼 수 있으면 그렇게 표시하고, 아닐 경우 JavaScript 객체 형태로 표시합니다.

> 주의: 이 기능은 Web Worker에서 사용할 수 없습니다

### console.error()

오류 메시지를 출력합니다. 추가 매개변수와 함께 문자열 치환을 사용할 수 있습니다.

### console.exception()

error()의 별칭입니다.

... 입력 중 https://developer.mozilla.org/ko/docs/Web/API/Console#%EB%A9%94%EC%84%9C%EB%93%9C

## 명세

[Console API](https://console.spec.whatwg.org/)
