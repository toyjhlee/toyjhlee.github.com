[link](https://y0c.github.io/2019/06/30/react-infinite-scroll/)
[link](https://upmostly.com/tutorials/build-an-infinite-scroll-component-in-react-using-react-hooks) - 해결법이 좋아 보인다

[link](https://im-developer.tistory.com/196)

- IntersectionObserver - Browser support](https://github.com/w3c/IntersectionObserver/tree/master/polyfill#browser-support)
  [Image Lazy Load 구현해 보기](https://medium.com/@pks2974/intersection-observer-%EA%B0%84%EB%8B%A8-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-fc24789799a3)

```
const options = { threshold: 0 };
const observer = new IntersectionObserver(
    (entries, observer) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting) {
                observer.unobserve(entry.target);
                entry.target.src = entry.target.dataset.src;
            }
        });
    }
, options);
observer.observe(
    Array.from(
        document.getElementsByClassName('lazy')
    )
);
```
