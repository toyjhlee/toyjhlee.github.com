---
title: "내가 사용하는 Visual Studio Code 초기 세팅"
date: 2020-08-25 20:12:00 +0900
categories: engineering
---

1. Remove trailing spaces automatically or with a shortcut
    - Menu File > Preference > Settings
        - 체크 : Files: Trim Trailing Whitespace

2. Extensions
    - GitLens
    - Vim
    - Markdown Preview Enhanced
    - Todo Tree
    - SVG Viewer
    - Prettier - Code Formatter

3. Prettier - 설정
    1. extionsion Prettier - Code Formatter 설치
    2. settings.josn 에 아래 속성 추가
        ```
        "editor.formatOnSave": true,
        ```
    3. sass 에 적용하지 않는다면git

        ```
            "editor.formatOnSave": true,
            "[scss]": {
            "editor.formatOnSave": false
            }
        ```

    3. .prettierrc.js 에 아래 코드 추가
        ```
        module.exports = Object.assign(require('kcd-scripts/prettier')
        ```

    4. .prettierrc.js 커스텀
        ```
        module.exports = Object.assign(require('kcd-scripts/prettier'), {
            tabWidth: 4,
            printWidth: 120,
        })
        ```
