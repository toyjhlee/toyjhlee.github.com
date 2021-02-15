---
title: 'JavaScript Generator'
tags: ['es6', 'generators', 'yield']
---

## 관련 글

[JavaScript Generator 이해하기](https://wonism.github.io/javascript-generator/)

[Generators in Javascript: How to use them
](https://dev.to/karimelghamry/generators-in-javascript-how-to-use-them-372d)

1. Use case 1: Mimic the range() function from Python
2. Use case 2: Visualize the Bubble Sort algorithm
3. Use case 3: Generate distinct random numbers on demand

## 문서

### yield

[mozilla yield](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/yield)

yield 키워드는 제너레이터 함수 (function\* 또는 레거시 generator 함수)를 중지하거나 재개하는데 사용됩니다.

```javascript
    function\* foo(){
        var index = 0;
        while (index <= 2)  // when index reaches 3,
                            // yield's done will be true
                            // and its value will be undefined;
            yield index++;
    }

    var iterator = foo();
    console.log(iterator.next()); // { value: 0, done: false }
    console.log(iterator.next()); // { value: 1, done: false }
    console.log(iterator.next()); // { value: 2, done: false }
    console.log(iterator.next()); // { value: undefined, done: true }
```

### yield\*

[mozilla yield\*](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/yield*)

-   yield\* 표현식은 다른 generator 또는 이터러블(iterable) 객체에 yield를 위임할 때 사용됩니다.
