##

고성과팀

[몇 가지는 나를 설명한다](https://brunch.co.kr/@vigorous21/662)

API, 디자인, 기획을 조합해서 결과물을 만들어 낸다

- 변경에 유연하다

## 이력

### calender

- SPA, front 단에서 Router 동작

### 청담

- 5년 6개월 간의 스타트업의 시작부터 상장까지
- 글로벌 서비스를 초장기 부터 프론트엔드 팀장으로 개발
- 디자이너와 디자인시스템 구축

  - 규칙이 모호한 디자인을 지속적인 협의를 통해 디자인 시스템 구축

- 불명확한 목표가 있을 때 의견을 취합해 POC 제작
- jQuery -> vue 변경
- Front-End 를 혼자로 시작해서 3명
  - 쥬니어를 리딩해서 프로젝트에 참여
- visual regression testing(시각적 회귀 테스트) BackstopJS 사용
- FLF frame work 제작

  - nodejs 기반의 backend 와 fontend 에서 같이 사용

  - 제한 적으로 사용 - css 를 리펙토링 할 때

- socket 통신으로 다른 유저가 입력하고 있는 걸을 보여줌

- 부족함

  - 일을 처리하는 것에 급급해 새로운 기술에 도입하는데 보수적이었다
  - 유하지 못 했음
  - 개발 외 적으로 구성원들의 의견을 반영하지 못 했음
    - E2E TEST 적용이 미흡
      - QUnit 작성 -> Selenium, Webdriver

- css, html, javascript

### 역삼

- 디자이너와 디자인시스템 구축

  - docz -> styleguidist 사용
    - 사이트에 접속해서 디자이너가 하나의 UX 에 각기 다른 case 를 볼 수 있어야 한다
  - 인클루시브 디자인

- 개발 프로세스 구축

  1. PM 이 이슈를 만든다
  2. 각 파트에서 검토 후 서브 테스크를 작성한다(디자인, 기획, Font-End, Back-End, 데이터 분석 등등)
  3. 서브 테스크는 검토를 거쳐서 소요시간을 기입한다
  4. 사전작업할 파트가 있다면 코멘트를 남긴다
  5. 각 파트가 다음 파트로 전달한 결과물의 기준을 정하게 했다.

- 조직원의 성장에 초점

  - 내가 하는게 아닌 문화화 과정을 만들어 진행하게 했다

- homepage

  - nextjs 로 개발
    https://linewalks.com/

- TEST 도입

  - enzyme, react-test-library 사용
  - 통과가 push 필수 조건

- 평가 제도 도입

  - 2달 간격으로 목표를 정한다

    - 3가지 방향(회사, 팀, 개인) 의 목표가 공유 된다

      - 서로의 목표를 공유하고 같은 방향으로 가게 끔 한다. 훗 날 오해가 쌓이지 않게 한다

        > 프로젝트 목표는 처음부터 분명하게 명시하고 프로젝트 참여자 모두가 주기적으로 되새겨야 한다.

        > 왜냐고? 조직에서 개개인의 추구하는 목표가 때로는 상충하기 때문이다.

        - [참고](/review/review-of-Adrenaline-Junkies-and-Template-Zombies/#71-크고-또렷하게)

- next.js 로 홈페이지 구축
- 회사관련 react framework 제작, 업데이트 환경 구축
- css, html, javascript

- 부족함
  - js 에 대비 css 의 경험이 부족함
  - TEST 를 작성해보지 않는 경우에는 작성 시간이 많이 소요

### 선릉

- 기존 회사와 다르게 퍼블리싱과 js 를 50%, 50% 정도 시간을 투입

- 시작부터 만든게 아닌 기존 코드 베이스로 개발

  - 코드를 분석 리팩토링, 테스트 코드 작성하면서 개발
  - 레거시된 코드를 개발자의 의도와 상황, 서비스 방향 등을 고려하면서 리팩토링 함

- 퍼블리셔와의 작업우

  - 처음하는 협업이라 그동안 사용하지 않는 속성들에 대해 고민하게 된 계기가 됨

- 디자이너와 디자인시스템 구축

  - 누락된 부분을 찾아서 디자이너에게 피드백 받고 작업하는 것을 반복
    - 시스템 구축에 경험이 없는 디자이너와 협업이라 천천히 설명하고 필요성을 느끼게 하면서 진행. 그래서 약간 더딘감이 없진 않았음

- styled-components 와 module.scss 사용
  - 이유 styled-components 로 만들어내는 style class 의 style 중복을 줄이고자
  ```
      const Button = styled.button.attrs((props: ButtonProps) => {
      return {
          ...props,
          className: [commonStyle.buttonInitStyle, commonStyle.buttonDefaultStyle].join(' '),
      }
  })``
  ```
- redux-persist sessionStorage 에 저장

  - migrate
    - Data 로드 후 API 변경 되었을 때 대비

- timeline 을 표현하는 bar 의 resize, drag 구현

  - 같은 y 축이 존재하는 bar 와 겹치면 안 된다
    - resize, drag 시 다른 bar 와 충돌 처리
      - 최적화하기 위해 resize 가 시작 될 때 좌우 최대 width 를 계산

- react 관련 이해도 상승
- 프로덕은 점진적향상법, 개발은 우아한 성능저하를 추구

  - 만들고 검증을 반복하는 과정에서는 점진적향상법
  - 프로덕과 디자인의 생각을 최대한 구현하기 위해 점짐적향상법으로 구현
  - IE 의 지원 중단으로 인해 polyfill 를 사용하는 우아한 성능저하를 추구

- lighthouse 를 사용한 최적화

### 장점

- “무엇을 아느냐”가 아니라 “어떻게 생각하느냐”라는 사실을 깨닫고 있다. [link](https://hyunseob.github.io/2016/02/21/how-to-become-a-great-frontend-engineer/)

  - 나는 지식을 가지고 결과를 만들어 낸다. 이제 그 지식의 필요성을 깨닿아서 다시금 학습하고 았다.
  - 그리고 용어에 대해 학습하고 있다.

- 낙관적, 긍정적
- 할수 있다는 자신감
- 주변 환경에 동요 되지 않음
- 공감 능력

### 나의 대해

- css, html, javascript
- 문화, 자동화, 프로세스
- [mochajs 기어](https://github.com/mochajs/mocha/blob/v7.0.1/CHANGELOG.md#book-documentation-4)

### 이력서 작성 시 참고

[react-ultimate-resume](https://github.com/welovedevs/react-ultimate-resume)

- 오픈 소스 맞춤형 개발자 이력서

## 발전을 하기 위해 하고 있는 것들

### blog 글 쓰기

- 그동안 누가 보기 부끄러워서 작성하지 못 했습니다. 나를 위해 작성하는 것으로 마음을 다잡고 작성하고 있습니다. 정확하게 알지 못 하는 것들, 좀 더 알게 된 사실들, 읽으면 좋은 것들, 책의 후기들 등등을 적고 있습니다

### 누군가의 질문에 대해 답해 주고 있습니다.

- 질문에 답하면서 또는 다른 이들의 답변을 보면서 성장하고 있습니다
- 올해는 목표는 스택오브 플로우에 답변을 하나 이상입니다.

<!-- ### 기존에 재직했던 회사의 오픈 소스에 기여를 하고 있습니다.

- 재직 중 만큼은 하지 못 하지만 2~3주에 하나씩 기여하려 하고 있습니다. -->

## 관심사

- 디자인 시스템 컴포넌트 개발
- 발전, 변화하는 기술
- Open API 개발
- 생산적인 문화
- 어떻게하면 더 잘 할 까?
