### 명령어

    - npm login 시 `401 unauthorized` 발생

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
