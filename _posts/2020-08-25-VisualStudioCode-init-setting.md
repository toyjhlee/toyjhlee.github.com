---
title: '내가 사용하는 Visual Studio Code 초기 세팅'
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
        ```javascript
        "editor.formatOnSave": true,
        ```
    3. sass 에 적용하지 않는다면git

        ```javascript
            "editor.formatOnSave": true,
            "[scss]": {
            "editor.formatOnSave": false
            }
        ```

    4. .prettierrc.json 에 kcd-scripts/prettier 를 복사

    5. .prettierrc.json 커스텀
        ```javascript
        {
            tabWidth: 4,
            printWidth: 120,
        }
        ```
    6. @trivago/prettier-plugin-sort-imports 추가
    7. settings.json // vs-code

        - save 시 prettier 가 동작하지 않아서 다음을 추가했다 esbenp.prettier-vscode

        ```javascript
        {
          "window.zoomLevel": 0,
          "files.trimTrailingWhitespace": true,
          "todo-tree.tree.showScanModeButton": false,
          "editor.formatOnSave": true,
          "editor.tabSize": 4,
          "editor.detectIndentation": false,
          "[scss]": {
              "editor.formatOnSave": false
          },
          "editor.defaultFormatter": "esbenp.prettier-vscode",
          "[javascript]": {
              "editor.defaultFormatter": "esbenp.prettier-vscode"
          }
          }
        ```
