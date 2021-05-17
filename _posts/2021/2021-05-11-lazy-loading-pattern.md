---
title: 'lazy loading'
---

[The lazy-loading property pattern in JavaScript](https://humanwhocodes.com/blog/2021/04/lazy-loading-property-pattern-javascript/)

-   3가지 패턴를 설명한다

## The messy lazy-loading property pattern

```es6
class MyClass {
    get data() {
        const actualData = someExpensiveComputation()

        Object.defineProperty(this, 'data', {
            value: actualData,
            writable: false,
            configurable: false,
            enumerable: false,
        })

        return actualData
    }
}

const object = new MyClass()
console.log(object.hasOwnProperty('data')) // false

const data = object.data
console.log(object.hasOwnProperty('data')) // true
```

## The only-own lazy-loading property pattern for classes

```es6
class MyClass {
    constructor() {
        Object.defineProperty(this, 'data', {
            get() {
                const actualData = someExpensiveComputation()

                Object.defineProperty(this, 'data', {
                    value: actualData,
                    writable: false,
                    configurable: false,
                })

                return actualData
            },
            configurable: true,
            enumerable: true,
        })
    }
}

const object = new MyClass()
console.log(object.hasOwnProperty('data')) // true

const data = object.data
console.log(object.hasOwnProperty('data')) // true
```

## The lazy-loading property pattern for object literals

```es6
const object = {
    get data() {
        const actualData = someExpensiveComputation()

        Object.defineProperty(this, 'data', {
            value: actualData,
            writable: false,
            configurable: false,
            enumerable: false,
        })

        return actualData
    },
}

console.log(object.hasOwnProperty('data')) // true

const data = object.data
console.log(object.hasOwnProperty('data')) // true
```
