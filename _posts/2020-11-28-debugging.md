### 디버깅 방법

-   나는 디버깅 방법에 대한 답변은 `이진탐색`을 이야기 했다. 듣는이는 와닫지 않는듯 보였다. 어떻게 하면 알려 줄 수 있을까하는 물음에 대한 설명들을 여기에 남긴다

-   [검증 된 디버깅 전략을 사용하여 이상한 버그를 해결하는 방법](https://css-tricks.com/heres-how-i-solved-a-weird-bug-using-tried-and-true-debugging-strategies/)

    1. 프로젝트의 세부사항을 검토 'First off, let’s consider the environment'
    2. 가설 형성 'Forming a hypothesis'
    3. 문제 단순화 'Problem simplification'
        - "버그와 관련이없는 코드 부분을 점진적으로 제거하는 접근 방식" [출처][debugging techniques]
    4. 문제 분리 'Isolating the issue'
        ```
        격리는 모든 디버깅에서 가장 강력한 핵심 원칙 일 수 있습니다. 우리의 코드베이스는 다양한 라이브러리, 프레임 워크로 확장 될 수 있으며 더 이상 프로젝트에서 작업하지 않는 사람들을 포함하여 많은 기여자를 포함 할 수 있습니다. 문제를 분리하면 문제의 중요하지 않은 부분을 천천히 제거하여 솔루션에 집중할 수 있습니다.
        ```
        - [감소 된 테스트 케이스 : Reduced Test Cases][reduced test cases]
    5. 재현 가능한 최소한의 예시 'A minimal reproducible example'
        - [최소한의 재현 가능한 예제를 만드는 방법 : How to create a Minimal, Reproducible Example][how to create a minimal, reproducible example]
    6. 나누고 해결 'Divide and conquer'
        - `여기 이진탐색이 나온다`
    7. 문제 해결 'Fixing the issue'

    8. 마무리 'Wrapping up'

        1. 문제를 단순화
        2. 문제 분리, 재현 가능한 최소한의 예시
        3. 나누고 해결

        ```
        버그에 너무 많은 시간을 할애하면 프로그래머가 지치고 디버깅이 역효과를 낼 수 있습니다. 휴식을 취하고 마음을 비우십시오. 휴식을 취한 후 다른 관점에서 문제에 대해 생각하십시오.
        ```

-   [디버깅 기법 : Debugging Techniques][debugging techniques]

    -   가장 좋은 방법 은 처음에 프로그램을 작성할 때 버그 를 피하는 것입니다! 코딩하기 전에 앉아서 생각하는 것이 중요합니다.

        -   설계 장점

            1. 깔끔한 디자인은 프로그램의 결함 가능성을 줄입니다.
            2. 테스트 중에 버그가 나타나더라도 명확한 불변성을 가진 깔끔한 디자인은 버그를 추적하고 수정하는 것을 훨씬 더 쉽게 만듭니다.

        -   버그 예방 및 방어 프로그래밍 'Bug Prevention and Defensive Programming'

            -   오류가 없는 프로그램 작성이 목표
            -   버그가 있다는 사실에 당황스럽게 생각해야한다

        -   결함의 종류 'Classes of Defects'

            -   Syntax or type errors
            -   Typos and other simple errors
            -   Implementation errors
            -   Logical errors

        -   어려움 'Difficulties'

            -   원인에 대한 명확한 표시를 제공하지 않는 경우
            -   재현하기 어려운 경우
            -   에러들이 서로 영향을 주는 경우
            -   에러 수정 시 다른 에러가 발생하는 경우

        -   디버깅 전략 'Debugging strategies'
            -   오류를 지역화하는 가장 효과적인 방법 중 하나는 프로그램을 점진적으로 개발하고 각 코드를 추가 한 후 자주 테스트하는 것입니다
            -   디버거를 사용하십시오.
            -   한 가지 옵션은 문제가 발생한 지점에서 시작하여 코드를 다시 살펴보고 어떻게 발생했는지 확인하는 것입니다.
            -   이진 검색
            -   문제 단순화
            -   과학적 방법 : 가설 형성
                1. 테스트 케이스 결과를 검사합니다
                2. 관찰 된 데이터와 일치하는 가설을 형성합니다
                3. 그런 다음 가설을 반박하는 간단한 테스트를 설계하고 실행합니다
                4. 가설이 반박 된 경우 다른 가설을 도출하고 프로세스를 계속하십시오.
            -   Bug clustering
                1. 많은 오류가보고되는 경우
                    - 관련 버그 (또는 유사한 버그)의 클래스로 그룹화하고 각 클래스에서 하나의 버그만 검사하는 것이 유용합니다.
            -   오류 감지 도구
                1.  생산성을 크게 높일 수 있지만 검사는 특정 도메인 또는 속성 클래스로 제한됩니다
        -   오류를 예상하는 위치에 대한 태도의 문제로 다른 여러 전략
            -   버그가 예상 한 곳에 있지 않을 수 있습니다. 특정 코드를 검사하는 데 많은 시간이 소요되었지만 오류가 없을 수 있습니다. 열린 마음을 가지고 프로그램의 다른 부분에 대해 질문하기 시작하십시오.
            -   버그가 어디에 있는지 스스로에게 물어보십시오. 때로는 문제를 거꾸로 보는 것이 다른 관점을 제공합니다. 종종 특정 장소에 버그가 없다는 것을 증명하려고하면 실제로 그 장소의 버그가 드러납니다.
            -   버그가 없다고 생각하는 이유를 자신이나 다른 사람에게 설명하십시오. 문제를 명확하게 설명하려고하면 버그를 발견 할 수 있습니다.
            -   입력 데이터를 검사하고 하네스(harness)를 테스트합니다. 테스트 케이스 또는 테스트 장치 자체가 손상되었을 수 있습니다. 이를주의 깊게 확인하고 버그가 실제 프로그램에 있는지 확인해야합니다.
            -   올바른 소스 코드가 있는지 확인하십시오. 디버깅중인 소스 코드가 실행중인 실제 프로그램과 일치하고 올바른 라이브러리가 연결되어 있는지 확인해야합니다
                -   일반적으로 몇 가지 간단한 확인이 필요합니다. makefiles 및 make 프로그램 (예 : Compilation Manager 및 .cm 파일)을 사용하면이 작업을 단일 명령 입력으로 줄일 수 있습니다.
            -   휴식을 취하다.
                -   버그에 너무 많은 시간을 할애하면 프로그래머가 지치고 디버깅이 역효과를 낼 수 있습니다.
                -   휴식을 취하고 마음을 비우십시오.
                -   휴식을 취한 후 다른 관점에서 문제에 대해 생각하십시오.

    -   위의 모든 것은 오류를 지역화하는 기술입니다
        -   오류가 확인되면 오류를 수정해야합니다
        -   어떤 경우에는 이것은 사소한 일입니다
        -   다른 경우에는 상당히 간단 할 수 있지만 변경은 특정 불변성을 유지해야합니다
        -   프로그래머는 수정 사항이 나머지 코드에 어떤 영향을 미칠지 잘 생각하고 오류를 수정하여 추가 문제가 발생하지 않도록해야합니다
        -   물론 이러한 불변성에 대한 적절한 문서화가 필요합니다
        -   마지막으로 알고리즘에서 개념적 오류를 나타내는 버그는 수정하기 가장 어렵습니다
        -   프로그래머는 알고리즘의 논리를 다시 생각하고 수정해야합니다.

-   [디버깅 팁과 요령][debugging-tips-tricks]
-   [감소 된 테스트 케이스 : Reduced Test Cases][reduced test cases]
-   [최소한의 재현 가능한 예제를 만드는 방법 : How to create a Minimal, Reproducible Example][how to create a minimal, reproducible example]

[debugging techniques]: https://www.cs.cornell.edu/courses/cs312/2006fa/lectures/lec26.html
[debugging-tips-tricks]: https://css-tricks.com/debugging-tips-tricks/
[how to create a minimal, reproducible example]: https://stackoverflow.com/help/minimal-reproducible-example
[reduced test cases]: https://css-tricks.com/reduced-test-cases/
