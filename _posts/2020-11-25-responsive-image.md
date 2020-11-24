-   [mozilla 반응형 이미지](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

    -   ````html
        <img
            srcset="elva-fairy-320w.jpg 320w, elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w"
            sizes="(max-width: 320px) 280px,
                      (max-width: 480px) 440px,
                      800px"
            src="elva-fairy-800w.jpg"
            alt="요정 옷을 입은 엘바"
        />
        ``` 위 속성들을 브라우저는 이렇게 할 것이다
        ````

    1. 기기 너비를 확인한다.
    2. sizes 목록에서 가장 먼저 참이 되는 미디어 조건문을 확인한다.
    3. 해당 미디어 쿼리가 제공하는 슬롯 크기를 확인한다.
    4. 해당 슬롯 크기에 가장 근접하게 맞는 srcset에 연결된 이미지를 불러온다.

    -   ```html
        <picture>
            <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg" />
            <source media="(min-width: 800px)" srcset="elva-800w.jpg" />
            <img src="elva-800w.jpg" alt="딸 엘바를 안고 서 있는 크리스" />
        </picture>
        ```

        -   <source> 요소에는 미디어 조건문이 있는 media 속성이 있다 — 처음에 살펴 봤던 srcset 예제처럼, 이 조건들도 어떤 이미지를 보여 줄 지 결정하는 데 사용한다 — 참을 리턴하는 첫 번째 것이 표시된다. 이 경우, 만약 뷰포트 너비가 799px 이하라면, 첫 번째 <source> 요소의 이미지가 표시될 것이다. 만약 뷰포트 너비가 800px 이상이라면, 두 번째 것을 보여 줄 것이다.
        -   srcset 속성에는 보여 줄 이미지 경로가 있었다. 위의 <img>에서 살펴 봤듯이, <source>도 여러 참조 이미지와 sizes 속성을 srcset 속성에 넣을 수 있다. 따라서 우리는 이미지 여러 개를 <picture> 요소에서 제공할 수 있다. 하지만 그렇게 되면 각각 다양한 해상도도 제공해야 할 것이다. 현실적으로, 이런 일을 자주 하고 싶지는 않을 것이다.
        -   이 모든 경우, src와 alt 속성이 있는 <img> 요소를 </picture> 바로 앞에 반드시 제공해야 한다. 그렇지 않으면 이미지가 표시되지 않을 것이다. 이것은 참을 리턴하는 미디어 조건문이 없는 경우 기본 이미지를 제공하는 것이다(실제 이 예제에서 두 번째 <source> 요소는 제거해도 된다). 그리고 <picture> 요소를 지원하지 않는 브라우저에 대체제를 제공하는 것이기도 하다.

    -   최신 이미지 포맷을 대담하게 사용하라
        -   흥미로운 새 이미지 포맷들이 있다(WebP나 JPEG-2000). 이 포맷들은 작은 용량과 높은 질을 동시에 유지할 수 있게 해 준다. 그러나 브라우저 지원에 구멍이 많다. <picture>는 상대적으로 낡은 브라우저들의 욕구도 채워 준다. 우리는 type 속성 안에 마임타입을 제공해 브라우저가 지원하지 않는 파일 유형을 즉시 거부하도록 할 수 있다.
            -   ```html
                <picture>
                    <source type="image/svg+xml" srcset="pyramid.svg" />
                    <source type="image/webp" srcset="pyramid.webp" />
                    <img src="pyramid.png" alt="정삼각형 4개로 만든 일반적인 피라미드" />
                </picture>
                ```
            -   아트 디렉션이 필요한 경우가 아니라면 media 속성을 사용하지 마라.
            -   <source> 요소에서, type에 유형을 선언한 이미지만 사용할 수 있다.
            -   앞서 다뤘듯, 필요에 따라 srcset과 sizes에 쉼표로 구분한 목록을 얼마든 사용할 수 있다.

-   [mozilla srcset](https://www.w3.org/TR/html51/semantics-embedded-content.html#element-attrdef-img-srcset)
-   [지원 여부 Srcset and sizes attributes](https://caniuse.com/srcset)
-   [지원 여부 picture](https://caniuse.com/picture)
-   [picturefill](https://scottjehl.github.io/picturefill/)
