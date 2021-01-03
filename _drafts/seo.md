## Google 검색 센터

### Google 검색에 내 웹사이트를 표시하는 방법

[link](https://developers.google.com/search/?hl=ko)

### Google에서 정보 삭제하기

[link](https://developers.google.com/search/docs/guides/advanced/remove-information?ref_topic=9427949&hl=ko)

### Google에 URL 재크롤링 요청하기

[link](https://developers.google.com/search/docs/advanced/crawling/ask-google-to-recrawl?hl=ko)

- URL 검사 도구 사용(소수의 URL을 제출하는 경우)
- 사이트맵 제출(한 번에 여러 URL을 제출하는 경우)

### 비즈니스 또는 마케팅 담당자

[link](https://developers.google.com/search/docs/beginner/get-started?hl=ko)

### 개발자

[link](https://developers.google.com/search/docs/beginner/get-started?hl=ko)

[link](https://developers.google.com/search/docs/guides/get-started?hl=ko)

## Naver Search Advisor

sitemap 등록 [link](https://searchadvisor.naver.com/)

웹페이지의 이동 [link](https://searchadvisor.naver.com/guide/seo-basic-redirect)

자바스크립트 검색 최적화 [link](https://searchadvisor.naver.com/guide/seo-advanced-javascript)

- SPA 사이트라도 HTML의 주요 영역 생성은 검색로봇이 잘 인식할 수 있도록 서버에서 렌더링 (Server Side Rendering)을 처리하는 것을 권장합니다

### 검색엔진 최적화 전문가

[link](https://developers.google.com/search/docs/advanced/guidelines/get-started?hl=ko)

## wepplication 의 내용

[검색엔진최적화(Search Engine Optimization, SEO)](https://wepplication.github.io/programming/seo/)

- sitemap.xml
- robot.txt
- 타이틀 & 메타디스크립션 태그
- 오픈그래프 태그
- 대표 주소 설정
- 이미지 태그 최적화
- 모바일 최적화
- HTTPS 보안 프로토콜 사용하기
- 웹페이지 로딩 속도 개선
- 동적 페이지 피하기
- 다국어 페이지 최적화

## sitemap.xml

### Google Search Central

[사이트 맵 작성 및 제출](https://developers.google.com/search/docs/advanced/sitemaps/build-sitemap)

### Sitemap XML 형식

[link](https://www.sitemaps.org/ko/protocol.html)

| 속성       | required | 설명                                                                                                                                                                                                                                                                                                         |
| ---------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| urlset     | true     | 파일을 캡슐화하고 현재 프로토콜 표준을 참조합니다.                                                                                                                                                                                                                                                           |
| url        | true     | 각 URL 항목의 상위 태그. 나머지 태그는 이 태그의 하위 태그입니다.                                                                                                                                                                                                                                            |
| loc        | true     | 페이지의 URL. 해당 URL은 http 같은 프로토콜로 시작해야 하며 웹서버에 따라 슬래시로 끝나야 합니다. 이 값은 2,048자 미만이어야 합니다.                                                                                                                                                                         |
| lastmod    | false    | 파일을 마지막으로 수정한 날짜입니다. 이 날짜는 W3C Datetime 형식이어야 합니다. 이 형식에서는 시간 부분을 생략할 수 있으며 원하는 경우 YYYY-MM-DD 형식을 사용할 수 있습니다. 이 태그는 서버에서 반환할 수 있는 If-Modified-Since(304) 헤더와 다르므로 검색 엔진은 두 소스에서 다른 정보를 사용할 수 있습니다. |
| changefreq | false    | 페이지가 변경되는 빈도. 이 값은 검색 엔진에 일반적인 정보를 제공하며 검색 엔진에서 페이지를 크롤링하는 정확한 빈도와는 관련이 없을 수도 있습니다. 유효한 값은 다음과 같습니다. always, hourly, daily, weekly, monthly, yearly, never. 태그의 값은 힌트 이지 명령이 아닙니다                                  |
| priority   | false    | 해당 사이트의 기타 URL에 대한 특정 URL의 상대적 우선순위.유효값 범위는 0.0-1.0입니다. 기본값은 0.5                                                                                                                                                                                                           |

#### Sitemap 색인 파일을 사용하여 여러 Sitemap 파일을 그룹화하기

여러 개의 Sitemap 파일을 제공할 수는 있지만 각 Sitemap 파일마다 URL을 50,000개까지만 포함할 수 있으며 파일 크기는 50MB(52,428,800바이트)를 초과할 수 없습니다.

## robots.txt

[robotstxt](http://www.robotstxt.org/)

## 알게 된 것

img 의 alt 값은 크롤링 대상이다. heading tag 가 없는 경우 img 의 Element 가 처음이라면 alt 값이 Title 이 될 수 있다

<!-- ![img element 가 처음에 오는 경우](/assets/img/2020/seo-img-alt.png) -->

## SPA SEO

### Google 검색 엔진이 단일 페이지 애플리케이션을 처리하는 방법을 이해

[SPA and SEO: Google (Googlebot) properly renders Single Page Application and execute Ajax calls](https://medium.com/@l.mugnaini/spa-and-seo-is-googlebot-able-to-render-a-single-page-application-1f74e706ab11)

[Core Principles of SEO for JavaScript](https://www.briggsby.com/dealing-with-javascript-for-seo)

[Optimizing Single-Page Applications: make your JavaScript site SEO-compatible](https://www.mindk.com/blog/optimizing-single-page-applications/)

[An SEO's survival guide to Single Page Applications (SPAs)](https://www.searchenginewatch.com/2018/04/09/an-seos-survival-guide-to-single-page-applications-spas/)
