---
title: 'front-end Test'
tags: ['test', 'tdd', 'bdd', 'ddd']
---

## 도입부

행복한 가정은 서로 닮았지만 불행한 가정은 모두 저마다의 이유로 불행하다 [톨스토이 - 안나 카레니나, 2011 번역 - 펭귄클래식코리아]

하나의 문제는 하나의 원인으로 이루어 지지 않는다

테스트는 deterministic 해야한다. (언제 실행되든 항상 같은 결과를 내야한다.)

## issue

`[Error: This browser does not support 'ResizeObserver' out of the box. Please provide a polyfill as a prop.]`

-   해결 `import 'resize-observer-polyfill/dist/ResizeObserver.global'`

## 관련 글들

### [정리 - 노트 클립 - 구글은 어떻게 소프트웨어를 테스트하는가](http://josephyeo.github.io/Testing/note_googletesting.html)

### [toast UI: 테스트](https://ui.toast.com/fe-guide/ko_TEST)

-   단위 테스트
    -   주로 모듈 단위
-   통합 테스트
    -   두 개 이상의 모듈이 연결된 상태를 테스트
-   E2E 테스트

    -   실제 사용자의 관점에서 테스트를 진행하며, 그런 의미에서 기능테스트 혹은 UI 테스트라고 불리기도 한다
    -   테스트 코드가 실제 코드 내부 구조에 영향을 받지 않기 때문에 큰 범위의 리팩토링에도 깨지지 않으며, 이를 통해 개발자들이 좀 더 자신감 있게 코드를 개선할 수 있도록 도와준다
    -   테스트 작성하기 어렵다
    -   테스트 사이의 중복이 발생한다
    -   예상 밖의 문제들(네트워크 오류, 프로세스 대기로 인한 타임아웃)으로 인해 테스트가 가끔 실패하는 일이 발생

-   [멀티 브라우저 테스트 환경 구축하기](https://ui.toast.com/weekly-pick/ko_20171020)
-   [Selenium WebDriver](https://ui.toast.com/fe-guide/ko_TEST#selenium-webdriver)

    -   WebDriver는 기본적으로 브라우저가 서버 역할을 하고 제어를 요청하는 기기(개발자 PC 혹은 CI 서버)가 클라이언트의 역할을 하는 서버-클라이언트 구조라고 할 수 있으며, 브라우저용 드라이버와 개발자용 클라이언트를 설치해서 사용하게 된다.

    -   E2E 테스트의 단점을 그대로 갖고 있기 때문에 테스트를 작성하거나 유지 보수하는데 많은 비용이 들며, 이로 인해 개발자들이 개발 단계에서 사용하는 테스트 도구로써는 사실상 널리 활용되지 못하고 있다.

    -   프레임워크
        -   Protractor : Angular 프로젝트를 위한 테스트 프레임워크
        -   WebdriverJS : Selenium Webdriver의 정식 Node.js 구현체이며, 낮은 수준(Low-level)의 API를 제공한다.
        -   NightWatch : Mocha 기반의 테스트 러너와 직관적인 API, CI 서버 통합 등의 다양한 기능을 지원한다.
        -   WebdriverIO : 테스트 러너, 정적 웹 서버, CI 서버 통합, REPL 인터페이스 등 다양한 기능을 지원하며 커뮤니티가 가장 잘 활성화되어 있다.

-   [Cypress](https://ui.toast.com/fe-guide/ko_TEST#cypress)
    -   Cypress는 Selenium WebDriver와는 전혀 다른 목적을 갖는 도구이며, 정확히 프론트엔드 개발자들이 개발 단계에서 사용하기에 최적화된 도구라고 할 수 있다
    -   WebDriver와는 다르게 실제 애플리케이션과 테스트 코드를 동일한 브라우저에서 실행하는 방식을 취하고 있다
    -   브라우저 기반의 GUI를 사용하여 테스트의 실행 상태를 확인하고 디버깅할 수 있는 다양한 편의 기능을 제공한다.
        -   실행된 모든 테스트 명령과 각 명령이 실행될 때의 UI 상태를 스냅샷 형태로 모두 저장하고 있어, 특정 시점의 UI 상태를 눈으로 확인할 수 있다
        -   또한 전체 테스트 진행 과정을 동영상으로 저장하거나 테스트가 실패했을 때 자동으로 스크린샷을 남길 수 있어 테스트가 실패했을 때 원인을 파악하기가 매우 쉽다
        -   게다가 브라우저에서 실행되기 때문에 필요한 경우 크롬 개발자 도구를 사용해 디버깅을 할 수도 있다.
    -   브라우저 내부에서 실행되는 방식에는 단점
        -   브라우저의 새 탭 혹은 새 창을 열 수 없으며
        -   동일 출처(Same-origin) 정책을 벗어나는 페이지로는 이동을 할 수가 없다

## 용어 정리

-   TDD: test driven development
-   BDD: Behaviour-Driven Development
    -   어떤 행위를 해야한다. (should do someting)
    -   BDD는 비즈니스 요구사항에 집중하여 테스트 케이스

## 경우에 관한 테스트 생각 by toyjhlee

-   lib
    -   lib 를 믿어라. input 이 올바른지 확인!

Test Runner Test Mathcher Test Mock

## Libaray

### reat-testing-library

#### [api-queries](https://testing-library.com/docs/dom-testing-library/api-queries)

#### [cheatsheet](https://testing-library.com/docs/dom-testing-library/cheatsheet#queries)

#### [testing-library / jest-dom - Custom matchers](https://github.com/testing-library/jest-dom#table-of-contents)

#### [examples](https://codesandbox.io/s/github/kentcdodds/react-testing-library-examples)

#### [React Unit Test — react-testing-library, 너를 알아가는 시간](https://medium.com/@juyeon.kate/react-unit-test-react-testing-library-%EB%84%88%EB%A5%BC-%EC%95%8C%EC%95%84%EA%B0%80%EB%8A%94-%EC%8B%9C%EA%B0%84-ab4ce30e6398)

-   Enzyme 에서 react-testing-library 변경 관련

#### `ReferenceError: document is not defined`

-   message

    ```
    The error below may be caused by using the wrong test environment, see https://jestjs.io/docs/en/configuration#testenvironment-string.
    Consider using the "jsdom" test environment.

    ReferenceError: document is not defined
    ```

-   해결방법

    -   [ReferenceError: document is not defined #422](https://github.com/testing-library/react-testing-library/issues/422#issuecomment-518007141)

    1. testEnvironment 를 node -> jsdom 으로 변경 in package.json
    2. jest 재 실행

#### `Property 'toBeInTheDocument' does not exist on type 'Matchers<any>`

-   message
    ```
    Property 'toBeInTheDocument' does not exist on type 'JestMatchersShape<HTMLElement[], Matchers<void, HTMLElement[]>, Matchers<Promise<void>, HTMLElement[]>>'.
    ```
-   해결방법

    -   [Property 'toBeInTheDocument' does not exist on type 'Matchers<any>'](https://stackoverflow.com/questions/57861187/property-tobeinthedocument-does-not-exist-on-type-matchersany)

    -   `import '@testing-library/jest-dom/extend-expect`

### jest

#### [daleseo.com](https://www.daleseo.com/jest-before-after/)

-   [Jest로 기본적인 테스트 작성하기](https://www.daleseo.com/jest-basic/)
-   [Jest로 테스트 전/후 처리하기](https://www.daleseo.com/jest-before-after/)
-   [Jest로 비동기 코드 테스트 작성하기](https://www.daleseo.com/jest-async/)
-   [[Jest] jest.fn(), jest.spyOn() 함수 모킹](https://www.daleseo.com/jest-fn-spy-on/)
-   [[Jest] jest.mock() 모듈 모킹](https://www.daleseo.com/jest-mock-modules/)

#### [snapshot-testing](https://jestjs.io/docs/en/snapshot-testing)

-   [왜 스냅 샷 테스트인가?](https://jestjs.io/blog/2016/07/27/jest-14.html#why-snapshot-testing)
    -   스냅 샷 통합 테스트가 해결하는 엔드 투 엔드 테스트에서 많은 문제를 발견했습니다.
        -   스냅 샷 테스트가 시각적 회귀 테스트 대비 장점
            -   결함 없음
            -   빠른 반복 속도
            -   디버깅
-   -u 플래그를 사용하여 스냅 샷을 다시 생성 할 수도 있습니다
-   toMatchInlineSnapshot
    -   스냅 샷 값이 소스 코드에 자동으로 다시 기록된다는 점을 제외하면 외부 스냅 샷 ( 파일) 과 동일하게 작동합니다 . 즉, 올바른 값이 기록되었는지 확인하기 위해 외부 파일로 전환하지 않고도 자동으로 생성 된 스냅 샷의 이점을 얻을 수 있습니다.

#### [Jest — How to Use Extend with TypeScript](https://medium.com/javascript-in-plain-english/jest-how-to-use-extend-with-typescript-4011582a2217)

```
declare global {
    namespace jest {
        interface Matchers<R> {
            withOut(expected: any): R
        }
    }
}

expect.extend({
    withOut(actual: any, expected: any) {
        const pass = actual % expected === 0
        const message = pass
            ? () => `expected ${actual} not to be without by ${expected}`
            : () => `expected ${actual} to be without by ${expected}`

        return {message, pass}
    }
})
```

#### canvas mock

```typescript
// setupTests.ts
import 'jest-canvas-mock'
```

#### getContext mock

[참고](https://github.com/jsdom/jsdom/issues/1782#issuecomment-337656878)

```javascript
function mockCanvas(window) {
    window.HTMLCanvasElement.prototype.getContext = function () {
        return {
            fillRect: function () {},
            clearRect: function () {},
            getImageData: function (x, y, w, h) {
                return {
                    data: new Array(w * h * 4),
                }
            },
            putImageData: function () {},
            createImageData: function () {
                return []
            },
            setTransform: function () {},
            drawImage: function () {},
            save: function () {},
            fillText: function () {},
            restore: function () {},
            beginPath: function () {},
            moveTo: function () {},
            lineTo: function () {},
            closePath: function () {},
            stroke: function () {},
            translate: function () {},
            scale: function () {},
            rotate: function () {},
            arc: function () {},
            fill: function () {},
            measureText: function () {
                return {width: 0}
            },
            transform: function () {},
            rect: function () {},
            clip: function () {},
        }
    }

    window.HTMLCanvasElement.prototype.toDataURL = function () {
        return ''
    }
}
```

```javascript
const document = jsdom.jsdom(undefined, {
    virtualConsole: jsdom.createVirtualConsole().sendTo(console),
})

const window = document.defaultView
mockCanvas(window)
```

#### worker mock

[참고](https://github.com/facebook/jest/issues/5023#issuecomment-351784414)

대상 코드

```javascript
import ExternalSourceLoaderWorker from "comlink-loader!./ExternalSourceLoaderWorker"; /
```

mock 코드

```javascript
jest.mock('../worker', () => {
    return jest.fn().mockImplementation(() => ({
        ExternalSourceLoaderWorker: jest.fn(),
    }))
})
```

#### private method mock

```javascript
class Foo {
    private prop: string;
}

const foo = new Foo()
jest.spyOn<any, string>(foo, 'prop');
```

#### Testing Sass with Jest

[참고](https://obyford.com/posts/testing-sass-with-jest/)

#### toHaveStyleRule 에 ruls 이 많은 경우

```javascript
const toHaveStyleRules = (component, property, options) => {
    let hyphen = ''
    _.each(property, (value, key) => {
        hyphen = key.replace(/([A-Z])/g, g => `-${g[0].toLowerCase()}`)
        expect(component).toHaveStyleRule(hyphen, value, options)
    })
}
```

#### window 에 값 설정

jest 실행 시 내부의 class 가 window 의 지정한 property 를 참조하는 경우 아래 방법으로는 undefind 가 발행한다

```
Object.defineProperty(window)
```

아래 방법으로 해야 한다

```
// setupTests
window.name = {

}
```

#### [Timer Mocks](https://jestjs.io/docs/en/timer-mocks)

-   [Jest Mock 타이머 적용하기](https://haeguri.github.io/2020/01/12/jest-mock-timer/)

```
jest.advanceTimersByTime(1000);
```

#### [7 Ways to Debug Jest Tests in Terminal](https://pragmaticpineapple.com/7-ways-to-debug-jest-tests-in-terminal/)

1. The Standard Way
2. Without an Initial Break
3. Debugging TypeScript Tests
4. Best Way To Debug ™️
5. What About CRA?
6. Debugging From the Command-Line
7. All-In-One solution - ndb

### visual regression testing(시각적 회귀 테스트)

-   [BackstopJS](https://github.com/garris/BackstopJS)

### E2E

-   [E2E 테스트](https://ui.toast.com/fe-guide/ko_TEST#e2e-%ED%85%8C%EC%8A%A4%ED%8A%B8)
-   [E2E 테스트와 나이트왓치](https://blog.coderifleman.com/2016/06/17/e2e-test-and-nightwatch/)
-   [Selenium에서 Cypress로 갈아탄 후기](https://medium.com/hbsmith/selenium%EC%97%90%EC%84%9C-cypress%EB%A1%9C-%EA%B0%88%EC%95%84%ED%83%84-%ED%9B%84%EA%B8%B0-324f224c14db)
    -   결론은 Cypress가 프런트엔드 개발자를 대상으로 한다는것과 Selenium은 QA개발자를 대상으로 한다는 것이 핵심이었다고 할 수 있다.

### robinwieruch

-   [react-testing-library](https://www.robinwieruch.de/react-testing-library)
-   [How to test React-Redux connected Components](https://www.robinwieruch.de/react-connected-component-test)
-   [How to test React with Jest & Enzyme](https://www.robinwieruch.de/react-testing-jest-enzyme)

### form 관련 예시 및 설명

-   [React Testing Library 사용법](https://www.daleseo.com/react-testing-library/)

[Difference between enzyme, ReactTestUtils and react-testing-library](https://stackoverflow.com/questions/54152562/difference-between-enzyme-reacttestutils-and-react-testing-library?answertab=active#tab-top)

### Redux

-   [Redux useSelector and useDispatch hook test example](https://gist.github.com/krawaller/e5d40217658fa132f3c3904987e467cd)

    -   [redux-mock-store](https://github.com/reduxjs/redux-mock-store) 사용
        -   `const configureStore = require('redux-mock-store').default`

-   [Writing Tests - Redux 공식홈](https://redux.js.org/recipes/writing-tests#connected-components)
-   [React + Redux 앱 테스트](https://velopert.com/3591)
-   [Unit Testing React-Redux Hooks - enzyme](https://medium.com/better-programming/unit-testing-react-redux-hooks-ce7d69e1e834)

-   [RTL with redux](https://dev.to/fredrikbergqvist/mocking-redux-useselector-hook-2ale)

-   [Testing Redux - reactjsday](https://noriste.github.io/reactjsday-2019-testing-course/book/react-testing-library/redux.html)

### 분류 전

-   [RTL로 HOC with React-Hooks 테스트 하기](https://pewww.tistory.com/25)

### 링크들

-   [입에 쓴 보약, TDD와 BDD - 2013.05 마소 VOL. 355-2013.05](https://kdata.or.kr/info/info_04_view.html?field=&keyword=&type=techreport&page=48&dbnum=172089&mode=detail&type=techreport)

    -   화성에서 온 TDD, 금성에서 온 BDD?

-   [번역 - 리액트 + 리덕스 앱을 Jest와 Enzyme으로 테스트 하며 얻은 교훈](https://rinae.dev/posts/lessons-learned-testing-react-redux-apps-with-jest-and-enzyme-kr)

    -   같은 환경이 아니어도 읽어볼 가치가 있다

-   Enzyme’s TDD approach and react-testing-library’s BDD

-   삭제 가능 할 듯 [Enzyme vs. react-testing-library: A mindset shift](https://blog.logrocket.com/enzyme-vs-react-testing-library-a-mindset-shift/)

    -   React-testing-library
        -   장점 : jest-dom 을 사용하여 좀 더 쉽게 만들 수 있음
        -   단점 : state 에 접근 할 수 없음
    -   logrocket 소개

-   [spearmint](https://github.com/open-source-labs/spearmint)
