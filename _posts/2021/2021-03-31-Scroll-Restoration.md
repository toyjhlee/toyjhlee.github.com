---
title: 'Scroll Restoration'
---

## Doc

[History API: Scroll Restoration](https://developers.google.com/web/updates/2015/09/history-api-scroll-restoration)

## Code

### React

```ts
function ScrollToTop({history}) {
    if (window.history.scrollRestoration === 'auto') {
        window.history.scrollRestoration = 'manual'
    }

    useEffect(() => {
        const unlisten = history.listen(() => {
            window.scrollTo(0, 0)
        })
        return () => {
            unlisten()
        }
    }, [])

    return null
}

export default withRouter(ScrollToTop)
```

## issue

[issue](http://toyjhlee.github.io/react-issue/#react-router-scroll-to-top)
