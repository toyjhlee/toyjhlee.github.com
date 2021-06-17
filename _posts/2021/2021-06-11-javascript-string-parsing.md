---
title: 'javascript string parsing'
---

## textNode 과 tag 분리

[Split string into words in javascript](https://stackoverflow.com/questions/18927223/split-string-into-words-in-javascript)

-   재귀는 안 됨

```js
var text = 'A wonderful serenity has taken possession of my entire soul. <strong>This is a subheadline</strong><br><br>I am alone, and feel the charm of existence in this spot.'

var elem = document.createElement('div')
elem.innerHTML = text

var array = []

for (var i = 0, childs = elem.childNodes; i < childs.length; i++) {
    if (childs[i].nodeType === 3 /* document.TEXT_NODE */) {
        array = array.concat(childs[i].nodeValue.trim().split(/\s+/))
    } else {
        array.push(childs[i].outerHTML)
    }
}
```

## 테그와 text를 한글자씩 분리

다음 정규식 사용 `/(?=[^>]*(?=<|$))/g`

```js
'aa<f class="">b<i alt="">c</i></f>'.split(/(?=[^>]*(?=<|$))/g)

-> ["a", "a", "<f class=\"\">", "b", "<i alt=\"\">", "c", "</i>", "</f>"]
```
