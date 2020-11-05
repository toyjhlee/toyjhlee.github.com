---
title: 'javascript 표준 내장 객체'
date: 2020-08-13 17:30:00 +0900
categories: engineering
---

### 사용하지 않았던 것, 정확히 몰랐던 것들의 리스트

-   사용하거나 알게 되면 삭제 (유예기간 1년)
-   해당 없으면 ~~cancelline~~ 표시

[AggregateError](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/AggregateError)

[Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)

-   Array.prototype.copyWithin()
    -   이해가 안 됨
-   Array.prototype.entries()
    -   next()
        -   done 이 true 시에도 계속 호출 가능
    -   반환 { value, done }
-   Array.prototype.flat()
    -   메서드는 모든 하위 배열 요소를 지정한 깊이까지 재귀적으로 이어붙인 새로운 배열을 생성
        -   [1, 2, [3, 4, [5, 6]]].flat() -> [1, 2, 3, 4, 5, 6]
        -   [1, 2, [3, 4, [5, 6]]].flat(Infinity)
-   Array.prototype.flatMap()
-   Array.prototype.splice()

[ArrayBuffer](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)

-   ArrayBuffer 객체는 일반적인 고정 길이 원시 이진 데이터 버퍼를 나타냅니다.

-   ArrayBuffer는 바이트로 구성된 배열로, 다른 언어에서는 종종 "바이트 배열"이라고 부릅니다. ArrayBuffer에 담긴 정보를 직접 수정하는 것은 불가능하지만, 대신 형식화 배열이나 [DataView](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/DataView) 객체를 통해 버퍼를 특정 형식으로 나타내고, 이를 통해 버퍼의 내용을 읽거나 쓸 수 있습니다.

-   ArrayBuffer() 생성자는 주어진 길이를 가진 새로운 ArrayBuffer를 생성합니다. 또한 Base64 문자열이나 로컬 파일처럼 기존 데이터에서 배열 버퍼를 생성할 수도 있습니다.

[AsyncFunction](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction)

-   AsyncFunction 생성자는 새로운 async function 객체를 만든다. 자바스크립트에서 모든 비동기 함수는 사실상 AsyncFunction 객체이다.

[Atomics](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Atomics)

-   본 기능은 아직 안정적인 크로스 브라우징에 도달하지 못했음

[BigInt](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt)

-   BigInt는 Number 원시 값이 안정적으로 나타낼 수 있는 최대치인 253 - 1보다 큰 정수를 표현할 수 있는 내장 객체입니다.
-   Number, Math 와 사용하면 정확성이 떨어질 수 있음
-   본 기능은 아직 안정적인 크로스 브라우징에 도달하지 못했음

[BigInt64Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt64Array)

[DataView](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/DataView)

-   DataView 뷰는 플랫폼의 자체 엔디언(바이트 정렬 방법)에 신경 쓰지 않으면서 ArrayBuffer에서 다양한 숫자 자료형의 데이터를 읽고 쓰기 위한 저수준 인터페이스를 제공합니다.
-   바이트 순서를 제어해야하는 경우 사용

[Error](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Error)

-   EvalError, InternalError, RangeError, ReferenceError, SyntaxError, TypeError, URIError
-   사용자 정의 에러 타입

[FinalizationRegistry](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry)

[Float32Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Float32Array)

[Float64Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Float64Array)

[Generator](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Generator)

-   Generator 객체는 generator function 으로부터 반환된 값이며 반복자와 반복자 프로토콜을 준수합니다.

[GeneratorFunction](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction)

-   Function 와 유사하다
-   IE 미지원

[Infinity](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Infinity)

[Int16Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Int16Array)

[InternalError](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/InternalError)

-   JavaScript 엔진 내부에서 발생한 에러를 나타냅니다
-   Chrome, IE 미지원

[Intl](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Intl)

-   Intl 객체는 각 언어에 맞는 문자비교, 숫자, 시간, 날짜비교를 제공하는, ECMAScript 국제화 API를 위한 이름공간입니다.
-   DateTimeFormat, ListFormat, NumberFormat, PluralRules, RelativeTimeFormat

[Map](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Map)

-   Map의 키는 정렬됩니다. 따라서 Map의 순회는 삽입순으로 이뤄집니다.
-   잦은 키-값 쌍의 추가와 제거에서 더 좋은 성능을 보입니다. Object 보다

[NaN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/NaN)

-   전역 NaN 속성은 Not-A-Number(숫자가 아님)를 나타냅니다.
    -   숫자로서 읽을 수 없음 (parseInt("어쩌구"), Number(undefined))
    -   결과가 허수인 수학 계산식 (Math.sqrt(-1))
    -   피연산자가 NaN (7 \*\* NaN)
    -   정의할 수 없는 계산식 (0 \* Infinity)
    -   문자열을 포함하면서 덧셈이 아닌 계산식 ("가" / 3)
-   NaN === Nan // false
-   isNaN(NaN) // true
-   [NaN].indexOf(NaN) // -1
-   [NaN].findIndex(isNaN) // 0

[Number](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number)

-   Number.EPSILON
    -   두 개의 표현 가능한 숫자 사이의 최소 간격.
-   Number.MAX_SAFE_INTEGER
    -   JavaScript에서 안전한 최대 정수. (2\*\*53 - 1)
-   Number.NEGATIVE_INFINITY
    -   음의 무한대를 나타내는 특수한 값. 오버플로우 시 반환됩니다.
-   Number.POSITIVE_INFINITY
    -   양의 무한대를 나타내는 특수한 값. 오버플로우 시 반환됩니다.
-   Number.isFinite()
    -   주어진 값이 유한수 인지 확인합니다.
-   Number.isInteger()
    -   주어진 값이 정수인지 확인합니다.
-   Number.isSafeInteger() 주어진 값이 안전한 정수인지 확인합니다.

[Object](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object)

-   Object.assign()
    -   하나 이상의 원본 객체들로부터 모든 열거가능한 속성들을 대상 객체로 복사합니다.
-   Object.create()
    -   주어진 프로토타입(prototype)의 객체와 속성들을 갖고 있는 새 객체를 생성합니다.
-   Object.seal()
    -   다른 코드가 객체의 속성을 삭제하지 못하도록 합니다.
-   Object.isSealed()
    -   객체가 실링(seal) 되었는지 확인합니다
-   Object.preventExtensions()
    -   객체가 확장되는 것을 못하도록 합니다.
-   Object.isExtensible()
    -   객체의 확장이 가능한지 확인합니다.
-   Object.freeze()
    -   객체를 프리징(freeze)합니다. 즉, 다른 곳의 코드에서 객체의 속성을 지우거나 바꿀 수 없습니다.
-   Object.isFrozen()
    -   객체가 프리징 되었는지 확인합니다.
-   Object .is()
    -   두 값이 같은 값인지 결정합니다
    -   ==, === 연산자의 결과값과 다름
-   Object.defineProperty()
    -   주어진 기술자(descriptor)에 의해 기술된(described) 이름붙은 속성을 객체에 추가합니다.
-   Object.defineProperties()
    -   주어진 기술자들에 맞는 이름붙은 속성들을 객체에 추가합니다.
-   Object.getOwnPropertyDescriptor()
    -   메서드는 주어진 객체 자신의 속성(즉, 객체에 직접 제공하는 속성, 객체의 프로토타입 체인을 따라 존재하는 덕택에 제공하는 게 아닌)에 대한 속성 설명자(descriptor)를 반환합니다.
-   Object.getOwnPropertyDescriptor()
    -   객체의 이름붙은 속성의 기술자를 반환합니다.
-   Object.getOwnPropertyNames()
    -   주어진 객체 자신만의 열거가능하거나 열거불가능한 속성들의 이름을 포함하는 배열(array)을 반환합니다.
-   Object.getOwnPropertySymbols()
    -   주어진 객체에서 바로 찾을 수 있는 모든 심볼 속성을 배열로 반환합니다.

[Promise](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise)

-   Promise는 다음 중 하나의 상태를 가집니다.
    -   대기(pending): 이행하거나 거부되지 않은 초기 상태.
    -   이행(fulfilled): 연산이 성공적으로 완료됨.
    -   거부(rejected): 연산이 실패함.
-   Promise.all(iterable)
-   Promise.race(iterable)
    -   iterable 내의 어떤 프로미스가 이행하거나 거부하는 즉시 스스로 이행하거나 거부하는 프로미스를 반환합니다. 이행 값이나 거부 이유는 원 프로미스의 값이나 이유를 그대로 사용합니다.
-   Promise.reject()

    ```
    Promise.reject("Testing static reject").then(function(reason) {
      // 호출되지 않음
    }, function(reason) {
      console.log(reason); // "Testing static reject"
    });

    Promise.reject(new Error("fail")).then(function(error) {
      // 호출되지 않음
    }, function(error) {
      console.log(error); // Stacktrace
    });
    ```

-   Promoise.resolve(); ``` const promise1 = Promise.resolve(123);

        promise1.then((value) => {
          console.log(value);
          // expected output: 123
        });

        ```

    [Proxy](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Proxy)

-   Proxy 객체는 기본적인 동작(속성 접근, 할당, 순회, 열거, 함수 호출 등)의 새로운 행동을 정의할 때 사용합니다.

[RangeError](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/RangeError)

-   RangeError 객체는 값이 집합에 없거나 허용되지 않은 값의 범위일 때 에러를 나타냅니다.
    -   Array 생성자로 허용범위를 초과한 길이의 배열 생성을 시도하려 하거나
    -   적절하지 않은 값을 numeric method(Number.toExponential(), Number.toFixed() 또는 Number.toPrecision())에 넘기려 할 때 이 에러를 만날 수 있을 것입니다.

[Reflect](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Reflect)

-   Reflect는 중간에서 가로챌 수 있는 JavaScript 작업에 대한 메서드를 제공하는 내장 객체입니다.
-   메서드의 종류는 프록시 처리기와 동일합니다.
-   Reflect는 함수 객체가 아니므로 생성자로 사용할 수 없습니다.
-   일부 메서드는 Object에도 존재하는 메서드이지만 [약간의 차이](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Reflect/Comparing_Reflect_and_Object_methods)가 있습니다.
    -   get 이외의 함에서 Object 는 객체를 반환하지만 Reflect 는 Boolean 를 반환하는 경우가 있다

[RegExp](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

-   정규 표현식을 사용해서 데이터 형식 바꾸기
    -   대치 문자열에는 $1과 $2를 사용하여 정규 표현식 패턴의 각 괄호에 일치한 결과를 받아옵니다.
    ```
    let re = /(\w+)\s(\w+)/
    let str = 'John Smith'
    let newstr = str.replace(re, '$2, $1')
    console.log(newstr)
    ```

[Set](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Set)

-   Set 객체는 자료형에 관계 없이 원시 값과 객체 참조 모두 유일한 값을 저장할 수 있습니다.

```
new Set([iterable]);
```

-   Set 객체는 값 콜렉션으로, 삽입 순서대로 요소를 순회할 수 있습니다. 하나의 Set 내 값은 한 번만 나타날 수 있습니다. 즉, 어떤 값은 그 Set 콜렉션 내에서 유일합니다.

```
new Set([1,2,1]) // [1, 2]
```

-   특히, +0 === -0이었지만 Set에서는 +0과 -0이 다른 값이었습니다. 그러나 이는 ECMAScript 2015 명세에서 변경되었습니다
-   원래 NaN !== NaN이지만, Set에서 NaN은 NaN과 같은 것으로 간주됩니다
-   add, clear, delete, entries, forEach, has, keys, values
-   Set.prototype[@@iterator]()

    ```
    const set1 = new Set();

    set1.add(42);
    set1.add('forty two');

    const iterator1 = set1[Symbol.iterator]();

    console.log(iterator1.next().value);
    // expected output: 42

    console.log(iterator1.next().value);
    // expected output: "forty two"
    ```

-   Array 객체와의 관계

```
var myArray = ['value1', 'value2', 'value3'];

// Array를 Set으로 변환하기 위해서는 정규 Set 생성자 사용
var mySet = new Set(myArray);

mySet.has('value1'); // true 반환

// set을 Array로 변환하기 위해 전개 연산자 사용함.
console.log([...mySet]); // myArray와 정확히 같은 배열을 보여줌
```

[SharedArrayBuffer](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer)

-   SharedArrayBuffer 객체는 제네릭, 고정된 길이의 원시 바이너리 데이터 버퍼를 표현하는데 사용됩니다. [ArrayBuffer](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) 객체와 유사하지만, 공유된 메모리상의 뷰를 생성하는데 사용될 수 있습니다. [ArrayBuffer](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) 와는 달리, SharedArrayBuffer 는 분리될 수 없습니다

[String](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String)

-   ECMAScript 2015 이후, 문자열 리터럴은 소위 템플릿 리터럴이 될 수 있습니다.
-   일부 다른 프로그래밍 언어와 달리, JavaScript는 작은따옴표와 큰따옴표 문자열을 구분하지 않습니다. 따라서 위의 이스케이프 문자는 작은따옴표나 큰따옴표에서 상관 없이 작동합니다.
-   이스케이프 표현
    -   \r 캐리지 리턴
    -   \f 폼 피드
-   문자열 원형과 String 객체의 차이

    -   JavaScript는 String 오브젝트와 원형의 문자열을 다르게 취급한다는 것에 주의해야 합니다. (Boolean과 숫자의 true도 마찬가지입니다.)

    -   JavaScript는 자동적으로 원형을 String 오브젝트로 변환하기 때문에, String 오브젝트 메서드를 사용하여 원형문자열을 생성할 수 있습니다. 문맥 안의 메서드에서 프로퍼티 조회 또는 원형의 문자열 호출이 발생하면, JavaScript는 자동으로 문자열 원형을 감싸고 프로퍼티 조회를 수행 하거나 메서드를 호출합니다.

    ```
    var s_prim = "foo";
    var s_obj = new String(s_prim);

    console.log(typeof s_prim); // Logs "string"
    console.log(typeof s_obj);  // Logs "object"
    console.log(typeof s_prim.valueOf()); // Logs "string"
    ```

    -   문자열 원형과 String 오브젝트는 eval()을 사용할 때 다른 결과를 제공합니다. eval에 전달되는 문자열 원형들은 소스 코드 취급을 받습니다; String 오브젝트들은 다른 모든 오브젝트들과 마찬가지로 취급하며, 오브젝트를 반환합니다.

    ```
    var s1 = '2 + 2';                // creates a string primitive
    var s2 = new String('2 + 2');    // creates a String object
    console.log(eval(s1));           // returns the number 4
    console.log(eval(s2));           // returns the string "2 + 2"
    console.log(eval(s2.valueOf())); // returns the number 4
    ```

-   메서드

    -   String.fromCharCode()
        -   지정된 유니코 값의 순서를 이용하여 만든 문자열을 반환합니다.
        ```
        console.log(String.fromCharCode(189, 43, 190, 61));
        // expected output: "½+¾="
        ```
    -   String.fromCodePoint()
        -   지정된 코드 포인트 순서를 이용하여 만든 문자열을 반환합니다.
        ```
        console.log(String.fromCodePoint(9731, 9733, 9842, 0x2F804));
        // expected output: "☃★♲你"
        ```
    -   String.raw()

        -   원형 템플릿 문자열(raw template string)에서 생성된 문자열을 반환합니다.

        ```
        const filePath = String.raw`C:\Development\profile\aboutme.html`;

        console.log(`The file was uploaded from: ${filePath}`);
        ```

-   String generic 메서드 `String generic들은 비표준으로, 가까운 미래에 사라질 것입니다. 아래에서 제공하고 있는 방식을 사용하지 않으면, 브라우저들간의 호환성은 기대하기 어렵습니다. `
    ```
    var num = 15;
    console.log(String.replace(num, /5/, '2'));
    ```
-   HTML wrapper methods
    -   anchor, big, blink, bold, fixed, fontcolor, fontsize, italics, link, smal, strike, sub, sup

[Symbol](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol)

-   Symbol() 함수는 심볼(symbol) 형식의 값을 반환하는데, 이 심볼은 내장 객체(built-in objects)의 여러 멤버를 가리키는 정적 프로퍼티와 전역 심볼 레지스트리(global symbol registry)를 가리키는 정적 메서드를 가지며, "new Symbol()" 문법을 지원하지 않아 생성자 측면에서는 불완전한 내장 객체 클래스(built-in object class)와 유사합니다.
-   Symbol()로부터 반환되는 모든 심볼 값은 고유합니다.
-   심볼 값은 객체 프로퍼티(object properties)에 대한 식별자로 사용될 수 있습니다; 이것이 심볼 데이터 형식의 유일한 목적입니다.
-   목적과 용례에 대한 더 자세한 설명은 [용어집의 심볼 항목(glossary entry for Symbol)](https://developer.mozilla.org/ko/docs/Glossary/Symbol)에서 볼 수 있습니다.

-   심볼(symbol) 데이터 형은 [원시 데이터 형(primitive data type)](https://developer.mozilla.org/ko/docs/Glossary/Primitive)의 일종입니다.

```
const symbol1 = Symbol();
const symbol2 = Symbol(42);
const symbol3 = Symbol('foo');

console.log(typeof symbol1);
// expected output: "symbol"

console.log(symbol2 === 42);
// expected output: false

console.log(symbol3.toString());
// expected output: "Symbol(foo)"

console.log(Symbol('foo') === Symbol('foo'));
// expected output: false
```

-   전역 심볼 레지스트리 내 공유 심볼
    -   Symbol() 함수를 사용한 위의 문법은 코드베이스(codebase) 전체에서 사용 가능한 전역 심볼을 생성하는 것은 아닙니다. 파일 간(across files), 또는 램(realms, 각각이 자체의 전역 범위(scope)를 가지는) 간에도 사용할 수 있는 심볼을 생성하기 위해서는, Symbol.for()와 Symbol.keyFor() 메서드를 이용해 전역 심볼 레지스트리에 심볼을 설정하거나 추출해야 합니다.
-   객체에서 심볼 속성(symbol properties) 찾기

    -   Object.getOwnPropertySymbols()
        -   모든 객체는 스스로에 대한 심볼 속성이 없는 상태로 초기화되기 때문에 해당 객체에 심볼 속성을 설정하기 전까지는 빈 배열을 반환한다는 점에 유의하시기 바랍니다.

-   잘 알려진 심볼들
    -   반복(iteration) 심볼
        -   Symbol.iterator
            -   객체의 기본 반복자(default iterator)를 반환하는 메서드.for...of에서 사용됨.
        -   Symbol.asyncIterator
            -   객체의 기본 비동기 반복자(default AsyncIterator)를 반환하는 메서드. for await of에서 사용됨.
    -   정규표현식 심볼
        -   match, replace, search, split
    -   그 외 심볼들
        -   [Symbol.hasInstance](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/hasInstance), [Symbol.isConcatSpreadable](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/isConcatSpreadable), [Symbol.unscopables](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables), [Symbol.species](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/species), [Symbol.toPrimitive](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toPrimitive), [Symbol.toStringTag](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag)
-   메서드
    -   [Symbol.for(key)](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/for)
        -   주어진 키(key)로 현재 존재하는 심볼을 검색하고 찾으면 반환합니다. 존재하지 않으면 주어진 키로 전역 심볼 레지스트리에 새로운 심볼을 생성하고 그 심볼을 반환합니다.
    -   [Symbol.keyFor(sym)](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol/keyFor)
        -   전역 심볼 레지스트리로부터 주어진 심볼에 대한 공유 심볼 키(shared symbol key)를 추출합니다.

[Classes](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Classes)
