---
title: 'ES6에 추가 된 것들'
date: 2020-07-21 16:29:00 +0900
categories: engineering
---

> 아래 URL 의 정보를 보기 내가 보기에 편하게 옮겨 적은 글

## 참고

-   원문 [ECMAScript 6 — New Features: Overview & Comparison][참고]
-   [번역1][번역1]
-   [번역2][번역2]
-   [번역3][번역3]

1. const

    - Constants

    ```javascript
    const PI = 3.141593
    ```

2. scope

    - Block-Scoped Variables
        - Block-scoped variables (and constants) without hoisting.
    - Block-Scoped Functions
        - Block-scoped function definitions.

3. arrow function

    - Expression Bodies
        - More expressive closure syntax
        ```javascript
        map(v => v + 1)
        ```
    - Statement Bodies
        - More expressive closure syntax
    - Lexical this
        - More intuitive handling of current object context.

4. Extended Parameter Handling

    - [Default Parameter Values](http://es6-features.org/#DefaultParameterValues)
    - [Rest Parameter](http://es6-features.org/#RestParameter)
    - [Spread Operator](http://es6-features.org/#SpreadOperator)

5. Template Literals

    - String Interpolation
    - Custom Interpolation
    - Raw String Access

6. Extended Literals

    - Binary & Octal Literal
    - Unicode String & RegExp Literal

7. Enhanced Regular Expression

    - Regular Expression Sticky Matching

8. Enhanced Object Properties

    - Property Shorthand
    - Computed Property Names
    - Method Properties

9. Destructuring Assignment

    - Array Matching
    - Object Matching, Shorthand Notation
    - Object Matching, Deep Matching
    - Object And Array Matching, Default Values
    - Parameter Context Matching
    - Fail-Soft Destructuring

10. Modules

    - Value Export/Import
    - Default & Wildcard

11. Classes

    - Class Definition
        - More intuitive, OOP-style and boilerplate-free classes.
    - Class Inheritance
        - More intuitive, OOP-style and boilerplate-free inheritance.
    - Class Inheritance, From Expressions
    - Base Class Access
        ```javascript
        super.xxx
        ```
    - Static Members
    - Getter/Setter

12. Symbol Type
    - Symbol Type
        ```javascript
        Symbol('foo') !== Symbol('foo')
        const foo = Symbol()
        const bar = Symbol()
        typeof foo === 'symbol'
        typeof bar === 'symbol'
        let obj = {}
        obj[foo] = 'foo'
        obj[bar] = 'bar'
        JSON.stringify(obj) // {}
        Object.keys(obj) // []
        Object.getOwnPropertyNames(obj) // []
        Object.getOwnPropertySymbols(obj) // [ foo, bar ]
        ```
    - Global Symbols
        ```javascript
        Symbol.for('app.foo') === Symbol.for('app.foo')
        ```
13. Iterators

    - Iterator & For-Of Operator

14. Generators

    ```javascript
    yield
    ```

15. Map/Set & WeakMap/WeakSet

    - Set Data-Structure

    ```javascript
    let s = new Set()
    s.add('hello').add('goodbye').add('hello')
    s.size === 2
    s.has('hello') === true
    for (let key of s.values()) // insertion order
        console.log(key)
    ```

    - Map Data-Structure

    ```javascript
    let m = new Map()
    let s = Symbol()
    m.set('hello', 42)
    m.set(s, 34)
    m.get(s) === 34
    m.size === 2
    for (let [key, val] of m.entries()) console.log(key + ' = ' + val)
    ```

    - Weak-Link Data-Structures
        - Memory-leak-free Object-key’d side-by-side data-structures.

16. Typed Arrays

    - Typed Arrays

17. New Built-In Methods

    - Object Property Assignment

    ```javascript
    Object.assign(dest, src1, src2)
    ```

    - Array Element Finding

    ```javascript
    ;[1, 3, 4, 2]
        .find(x => x > 3) // 4
        [(1, 3, 4, 2)].findIndex(x => x > 3) // 2
    ```

    - String Repeating

    ```javascript
    'foo'.repeat(3)
    ```

    - String Searching

    ```javascript
    'hello'.startsWith('ello', 1) // true
    'hello'.endsWith('hell', 4) // true
    'hello'.includes('ell') // true
    'hello'.includes('ell', 1) // true
    'hello'.includes('ell', 2) // false
    ```

    - Number Type Checking

    ```javascript
    Number.isNaN()
    Number.isFinite()
    ```

    - Number Safety Checking

    ```javascript
    Number.isSafeInteger()
    ```

    - Number Comparison

    ```javascript
    Number.EPSILON
    ```

    - Number Truncation

    ```javascript
    console.log(Math.trunc(42.7)) // 42
    console.log(Math.trunc(0.1)) // 0
    console.log(Math.trunc(-0.1)) // -0
    ```

    - Number Sign Determination

18. Promises

    - Promise Usage
    - Promise Combination

19. Meta-Programming

    - Proxying

    ```javascript
    let target = {
        foo: 'Welcome, foo',
    }
    let proxy = new Proxy(target, {
        get(receiver, name) {
            return name in receiver ? receiver[name] : `Hello, ${name}`
        },
    })
    proxy.foo === 'Welcome, foo'
    proxy.world === 'Hello, world'
    ```

    - Reflection

    ```javascript
    let obj = {a: 1}
    Object.defineProperty(obj, 'b', {value: 2})
    obj[Symbol('c')] = 3
    Reflect.ownKeys(obj) // [ "a", "b", Symbol(c) ]
    ```

20. Internationalization & Localization
    - Collation
        - Sorting a set of strings and searching within a set of strings. Collation is parameterized by locale and aware of Unicode.
    - Number Formatting
    ```javascript
    var l10nEN = new Intl.NumberFormat('en-US')
    var l10nDE = new Intl.NumberFormat('de-DE')
    l10nEN.format(1234567.89) === '1,234,567.89'
    l10nDE.format(1234567.89) === '1.234.567,89'
    ```
    - Currency Formatting
    ```javascript
    var l10nUSD = new Intl.NumberFormat('en-US', {style: 'currency', currency: 'USD'})
    l10nUSD.format(100200300.4) === '$100,200,300.40'
    ```
    - Date/Time Formatting
    ```javascript
    var l10nEN = new Intl.DateTimeFormat('en-US')
    l10nEN.format(new Date('2015-01-02')) === '1/2/2015'
    ```

[참고]: http://es6-features.org/#DefaultParameterValues
[번역1]: https://isme2n.github.io/devlog/2017/04/28/es6/
[번역2]: https://isme2n.github.io/devlog/2017/04/29/es6-2/
[번역3]: https://isme2n.github.io/devlog/2017/05/03/es6-3/
