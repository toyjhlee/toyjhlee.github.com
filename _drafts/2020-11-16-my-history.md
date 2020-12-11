### 청담

- 5년 6개월 간의 스타트업의 시작부터 상장까지
- 디자이너와 디자인시스템 구축
- 불명확한 목표가 있을 때 의견을 취합해 POC 제작
- jQuery -> vue 변경
- Front-End 를 혼자로 시작해서 3명
  - 쥬니어를 리딩해서 프로젝트에 참여
- visual regression testing(시각적 회귀 테스트) BackstopJS 사용

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

- TEST 도입

  - enzyme, react-test-library 사용
  - 통과가 push 필수 조건

- next.js 로 홈페이지 구축
- 회사관련 react framework 제작, 업데이트 환경 구축
- css, html, javascript

- 부족함
  - js 에 대비 css 의 경험이 부족함
  - TEST 를 작성해보지 않는 경우에는 작성 시간이 많이 소요

### 선릉

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
- redux-persist 사용하여 서버로 보내기 전에 저장

  - migrate
    - Data 로드 후 API 변경 되었을 때 대비

- timeline 을 표현하는 bar 의 resize, drag 구현
  - 같은 y 축이 존재하는 bar 와 겹치면 안 된다
    - resize, drag 시 다른 bar 와 충돌 처리
      - 최적화하기 위해 resize 가 시작 될 때 좌우 최대 width 를 계산

### 장점

- “무엇을 아느냐”가 아니라 “어떻게 생각하느냐”라는 사실을 깨닫고 있다. [link](https://hyunseob.github.io/2016/02/21/how-to-become-a-great-frontend-engineer/)
  - 나는 지식을 가지고 결과를 만들어 낸다. 이제 그 지식의 필요성을 깨닿아서 다시금 학습하고 았다.
  - 그리고 용어에 대해 학습하고 있다.
  -
