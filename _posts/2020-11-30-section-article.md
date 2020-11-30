### section: 일반 구획 요소

-   HTML \<section\> 요소는 HTML 문서의 독립적인 구획을 나타내며, 더 적합한 의미를 가진 요소가 없을 때 사용합니다. 보통 \<section\>은 제목을 포함하지만, 항상 그런 것은 아닙니다. [mozilla](section)

### article

-   HTML \<article\> 요소는 문서, 페이지, 애플리케이션, 또는 사이트 안에서 독립적으로 구분해 배포하거나 재사용할 수 있는 구획을 나타냅니다. 사용 예제로 게시판과 블로그 글, 매거진이나 뉴스 기사 등이 있습니다. [mozilla](article)

    -   사용 일람
        -   각각의 \<article\>을 식별할 수단이 필요합니다. 주로 제목(\<h1\>-\<h6\>) 요소를 \<article\>의 자식으로 포함하는 방법을 사용합니다.
        -   \<article\> 요소가 중첩되어 있을 때, 안쪽에 있는 요소는 바깥쪽에 있는 요소와 관련된 글을 나타냅니다. 예를 들어 블로그 글의 댓글은, 글을 나타내는 \<article\> 요소 안에 중첩한 \<article\>로 나타낼 수 있습니다.
        -   \<article\> 요소의 작성자 정보를 \<address\> 요소를 이용하여 제공할 수 있습니다. 그러나 중첩 \<article\>에는 적용되지 않습니다.
        -   \<article\> 요소의 작성일자와 시간은 \<time\> 요소의 datetime 속성을 이용하여 설명할 수 있습니다. 참고로 \<time\> 요소의 pubdate 속성은 더 이상 W3C HTML5 표준안에 포함되지 않습니다.

[section]: https://developer.mozilla.org/ko/docs/Web/HTML/Element/section
[article]: https://developer.mozilla.org/ko/docs/Web/HTML/Element/article

### <section> 버리고 HTML5 <article> 써야 하는 이유

-   [link](https://webactually.com/2020/03/03/%3Csection%3E%EC%9D%84-%EB%B2%84%EB%A6%AC%EA%B3%A0-HTML5-%3Carticle%3E%EC%9D%84-%EC%8D%A8%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0/)
