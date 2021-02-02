---
title: '글 쓰기 전'
---

[Why the iPhone Timer App displays a Fake Time](https://lukashermann.dev/writing/why-the-iphone-timer-displays-fake-time/)

> 시간을 표현하는 것에 오차를 줄이는 아이디어

-   결론 다음 처럼 전처리 한 후 계산 `parseInt(new Date().getTime() / 1000) * 1000`
