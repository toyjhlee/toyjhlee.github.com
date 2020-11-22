### 명령어

-   npm login 시 `401 unauthorized` 발생

### 에러

    ```
    npm adduser
    Username: (developer) toyjhlee
    Password: (<default hidden>)
    Email: (this IS public) (han@xxx.com) toyjhlee@gmail.com
    npm ERR! code E401
    npm ERR! 401 Unauthorized - PUT http://repo.xxx.co.kr/repository/npm-public/-/user/org.couchdb.user:toyjhlee - Bad username or password

    npm ERR! A complete log of this run can be found in:
    npm ERR!     /Users/junghanlee/.npm/_logs/2020-11-03T14_00_44_919Z-debug.log
    ```

#### 해결

    - 참고 [링크](https://github.com/npm/npm/issues/19735) `npm config set registry https://registry.npmjs.org/`

#### 명령어

    npm publish

### 에러

    ```
    npm ERR! code E402
    npm ERR! 402 Payment Required - PUT https://registry.npmjs.org/@toyjhlee%2freact-tag-input - You must sign up for private packages

    npm ERR! A complete log of this run can be found in:
    npm ERR!     /Users/junghanlee/.npm/_logs/2020-11-03T14_08_24_457Z-debug.log
    ```

#### 해결

    `npm publish --access=public`

#### 명령어

    `npm publish --access=public`

#### 에러

    ```
    npm ERR! code E403
    npm ERR! 403 403 Forbidden - PUT https://registry.npmjs.org/@toyjhlee%2freact-tag-input - you must verify your email before publishing a new package: https://www.npmjs.com/email-edit
    npm ERR! 403 In most cases, you or one of your dependencies are requesting
    npm ERR! 403 a package version that is forbidden by your security policy.
    ```

#### 해결

    email 인증

#### 명령어

    npm publish --access=public

#### 에러

    ```
    npm ERR! code E403
    npm ERR! 403 403 Forbidden - PUT https://registry.npmjs.org/react-ui - You do not have permission to publish "react-ui". Are you logged in as the correct user?
    npm ERR! 403 In most cases, you or one of your dependencies are requesting
    npm ERR! 403 a package version that is forbidden by your security policy.

    npm ERR! A complete log of this run can be found in:
    npm ERR!     /Users/junghanlee/.npm/_logs/2020-11-09T13_58_14_688Z-debug.log
    ```

#### 해결

-   npm 패키지 이름을 겹치지 않게 수정 [참고 링크](https://thebook.io/080229/ch05/05-01/)

#### Example

-   [How to Create a Typescript and React Module](https://www.pluralsight.com/guides/react-typescript-module-create)
    -   에러 발생 `/build/index.tsx' is not a module.ts(2306)`
    -   해결 방법 : 찾는 중 ...
    -   Tip : build 해서 작업 중인 곳에서 확인 해보면 된다 ....

#### unpublish

-   `pm unpublish <pkg> --force`
-   [문서 npm-unpublish](https://docs.npmjs.com/cli/v6/commands/npm-unpublish)

#### semantic-release

-   [github](https://github.com/semantic-release/semantic-release)

#### 에러

```
You cannot publish over the previously published version. Try bumping the version to
```

### 원인

-   unpublish 한 동일 package 의 version 정보 보다 높아야 한다
-   [npm github](https://github.com/npm/npm/issues/9266)

### 해결

-   원인에 포함되어 있음

### Webpack

-   [Webpack에서 Tree Shaking 적용하기](https://medium.com/naver-fe-platform/webpack%EC%97%90%EC%84%9C-tree-shaking-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-1748e0e0c365)

    -   Tree Shaking은 사용하지 않는 코드를 제거함으로써 용량을 줄일 수 있는 방식입니다.

-   [Webpack 4의 Tree Shaking에 대한 이해](https://huns.me/development/2265)
