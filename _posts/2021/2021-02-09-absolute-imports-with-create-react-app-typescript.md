---
title: 'Absolute paths with Create React App + Typescript (without ejecting)'
---

## 설정

craco 선택 이유 성공해서...

[Why I built CRACO](https://medium.com/gsoft-tech/why-i-built-craco-33ff39f4fc94)

### install
// craco 6.0.0 버전에서는 react-script 를 4.x.x 로 업데이트 해야 한다
npm install @craco/craco@5.8.0 craco-alias@2.1.1 --save-dev

#### 다운그레이드 이유는 아래 에러를 해결하기 위해서다
`TypeError: Cannot add property paths, object is not extensible`
다음 방법을 [참조](https://github.com/risenforces/craco-alias/issues/21) 했다


## 파일 추가 및 수정
root 에 craco.config.js, tsconfig.paths.json 생성

```
// craco.config.js

const CracoAlias = require("craco-alias");

module.exports = {
  plugins: [
    {
      plugin: CracoAlias,
      options: {
        source: "tsconfig",
        // baseUrl SHOULD be specified
        // plugin does not take it from tsconfig
        baseUrl: "./",
        // tsConfigPath should point to the file where "baseUrl" and "paths" are specified
        tsConfigPath: "./tsconfig.paths.json"
      }
    }
  ]
};
```

```
// tsconfig.paths.json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

```
// tsconfig.json 수정
{
  {
  "extends": "./tsconfig.paths.json",
  "compilerOptions": {
    "noFallthroughCasesInSwitch": true,
  }
}
```

## 사용
```
import app from '@/app'
```

## 성공


## 그외

### react-script update
[Migrating from 3.4.x to 4.0.0](https://github.com/facebook/create-react-app/blob/master/CHANGELOG.md#migrating-from-34x-to-400)

### sass

위 방법에는 필요 없다

[craco.config.js](https://github.com/gsoft-inc/craco/blob/9f4077d8f7718158142636d47d39a862d5877df5/recipes/use-dart-sass/craco.config.js)

### react-app-rewired 을 사용한 방법
[Absolute paths with Create React App + Typescript (without ejecting)](https://medium.com/@gustavograeff1998/absolute-imports-with-create-react-app-typescript-e87878cab65b)

## 참고한 링크들

감사합니다

- [create-react-app-typescript 상대경로를 절대경로로 바꾸기 v2](https://kod4284.github.io/2020/03/08/CRAT-setting-absolute-path-v2/)
- [CRA + Typescript 절대경로 설정 (w/craco)](https://howdy-mj.me/typescript/craco-absolute-paths-setting/)
