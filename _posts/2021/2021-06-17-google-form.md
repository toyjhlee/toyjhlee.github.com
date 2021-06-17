---
title: 'Google form'
---

[Embedding Google Forms in a Static Site](https://spin.atomicobject.com/2021/05/20/embedding-google-forms/)

```js
function handleSubmit(event) {
    const googleFormEndpoint = 'https://docs.google.com/forms/.../formResponse'
    let request = new XMLHttpRequest()
    request.open('POST', googleFormEndpoint, true)

    request.onload = function () {
        // handle request sent successfully
    }

    request.onerror = function () {
        // handle request failed to send
    }

    request.send(new FormData(event.target))
    event.preventDefault()
}
```
