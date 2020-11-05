npm login 시 `401 unauthorized` 발생

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

-   해결 방법 참고 [링크](https://github.com/npm/npm/issues/19735) `npm config set registry https://registry.npmjs.org/`

```
npm ERR! code E402
npm ERR! 402 Payment Required - PUT https://registry.npmjs.org/@toyjhlee%2freact-tag-input - You must sign up for private packages

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/junghanlee/.npm/_logs/2020-11-03T14_08_24_457Z-debug.log
```

`npm publish --access=public`

```
npm ERR! code E403
npm ERR! 403 403 Forbidden - PUT https://registry.npmjs.org/@toyjhlee%2freact-tag-input - you must verify your email before publishing a new package: https://www.npmjs.com/email-edit
npm ERR! 403 In most cases, you or one of your dependencies are requesting
npm ERR! 403 a package version that is forbidden by your security policy.
```

-   email 인증 하지 않아서 발생

-   인증

-   publish 성공
