---
title: 'storybook setup'
---

## 환경

create-react-app typescript

## 설치

storybook 설치 px -p @storybook/cli sb init

[@storybook/cli](https://www.npmjs.com/package/@storybook/cli)

## 설정

### storybook 에서 alias path 설정

[참고 url](https://github.com/storybookjs/storybook/issues/3916#issuecomment-664349094)

```
# /root/.storybook/webpack.config.js

const path = require("path");

module.exports = ({ config }) => {
  config.resolve.alias = {
    ...config.resolve.alias,
    "@src": path.resolve(__dirname, "../src"),
  };

  return config;
};
```

## Addon

[Storybook을 다양한 Addon과 함께 활용해보면서 사용법 정복하기](https://velog.io/@velopert/start-storybook)
