---
title: 'javascript momory'
---

## 개요

mozilla [자바스크립트의 메모리관리](https://developer.mozilla.org/ko/docs/Web/JavaScript/Memory_Management)

### 메모리 생존주기

메모리 생존주기는 프로그래밍 언어와 관계없이 비슷하다.

1. 필요할때 할당한다.
2. 사용한다. (읽기, 쓰기)
3. 필요없어지면 해제한다. 두 번째 부분은 모든 언어에서 명시적으로 사용된다. 그러나 첫 번째 부분과 마지막 부분은 저수준 언어에서는 명시적이며, 자바스크립트와 같은 대부분의 고수준 언어에서는 암묵적으로 작동한다.

### 데이터 할당의 동작원리

## 설명

[당신이 모르는 자바스크립트의 메모리 누수의 비밀](https://ui.toast.com/weekly-pick/ko_20210611)

### 클로저가 메모리 누수

```js
function fn1() {
    let a = new Array(10000)

    let b = 3

    function fn2() {
        let c = [1, 2, 3]
    }

    fn2()

    return a
}

let res = []

function myClick() {
    res.push(fn1())
}
```

### 분리된 DOM 노드

```js
let btn = document.querySelector('button')
let child001 = document.querySelector('.child001')
let root = document.querySelector('#root')

btn.addEventListener('click', function () {
    root.removeChild(child001)
})
```

### 콘솔 출력

```js
document.querySelector('button').addEventListener('click', function () {
    let obj = new Array(1000000)

    console.log(obj)
})
```

### 해제 하지 않은 타이머

```js
function fn1() {
    let largeObj = new Array(100000)

    setInterval(() => {
        let myObj = largeObj
    }, 1000)
}

document.querySelector('button').addEventListener('click', function () {
    fn1()
})
```

## 관련 함수

-   [AbortController](https://developer.mozilla.org/ko/docs/Web/API/AbortController)

```jsx
useEffect(() => {
    let abortController = new AbortController()
    const fetchData = async () => {
        try {
            const response = await fetch('https://jsonplaceholder.typicode.com/todos/1', {
                signal: abortController.signal,
            })
            const newData = await response.json()
            setTodo(newData)
        } catch (error) {
            if (error.name === 'AbortError') {
                // requset를 abort하는 과정에서 에러 발생
            }
        }
    }
    fetchData()
    return () => {
        abortController.abort()
    }
}, [])
```

### IE 6 ~ 7 메모리 누수

```js
// 순환 참조 코드
// 정상적인 엔진은 이것을 Closure로 이해하며 엘리먼트가
// 참조를 잃을 경우 카비지 컬렉팅 된다.
// 그러나 JScript 는 순환 참조로 인식하여
// 서로 참조를 기억하고 컬렉팅되지 않는다.
var actionButton = document.createElement('button')
actionButton.innerHTML = 'Click Me'

var pullhandler = function (e) {
    // Element가 Handler에서 참조. Closure.
    actionButton.innerHTML = 'Pushed'
    pullContent()
}
// Handler를 Element 가 참조.
actionButton.onclick = pullhandler

document.body.appendChild(actionButton)
```

[위 코드 출처](https://blog.javarouka.me/2012/07/30/event-ie/)

[JavaScript Memory Profiling](https://www.slideshare.net/OhgyunAhn/java-script-memoryprofiling)

#### DOM 과 이벤트 핸들러의 순환참조 설명

-   page 25 [Memory Leaks In Internet Explorer](https://www.slideshare.net/tifftiff/memory-leaks-in-ie)
