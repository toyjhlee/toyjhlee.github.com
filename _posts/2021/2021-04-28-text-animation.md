---
title: 'Text Animation'
---

## 문서

[Web Animations](https://www.w3.org/TR/web-animations/)

-   W3C Working Draft, 18 May 2021

## css

css animation 을 사용하는 방법

[CSS 애니메이션 사용하기](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Animations/Using_CSS_animations)

## Lottie

Lottie 는 AfterEffects 의 작업물을 Bodymovin 플러그인을 사용하여 json 으로 변환하고, 이 변환된 json 을 web 상에 렌더링하는 lib

json 을 수정해서 text 를 수정 할 수 있다

[text 변경 example](https://codepen.io/airnan/pen/ZLVJmq)

## Restart css animation

### 내가 사용한 방법

::after, ::before 의 style 을 변경하는 방법을 못 찾아서 아래와 같이 css custom property 을 사용하여 처리 했다.

```javascript
target.style.removeProperty('--animation-name')
void target.offsetWidth
target.style.setProperty('--animation-name', `${animationName}`)
```

### 다른 방법 1

```
target.classList.remove('classname')
setTimeout(function(){
  target.classList.add('classname')
},1)
```

### 다른 방법 2

```javascript
target.classList.remove('classname')
void target.offsetWidth
target.classList.add('classname')
```

### 다른 방법 3

```javascript
target.style.animationPlayState = 'paused'
target.style.animationPlayState = 'running'
```

### 가상요소(Pseudo-Element) 스타일 가져오기

여담으로 ::aftert 의 스타일은 아래와 같은 방법으로 참조할 수 있다

```javascript
var color = window.getComputedStyle(document.querySelector('.element'), ':before').getPropertyValue('color')
```

## CSS Custom property Polyfill

[CSS Variables Polyfill for IE11](https://github.com/nuxodin/ie11CustomProperties)

## 참고 URL

-   [Restart CSS Animation](https://css-tricks.com/restart-css-animation/)
