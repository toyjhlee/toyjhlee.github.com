---
title: 'html audio'
tags: ['audio']
---

> Audio 관련을 모아 둔다

## Audio Tag

-   [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery#Web_Audio_API)

## Visualizations Audio

### API 설명

[Visualizations with Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Visualizations_with_Web_Audio_API)

[Web Audio API 간단 정리하기](https://medium.com/@pks2974/web-audio-%EA%B0%84%EB%8B%A8-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-952a19d6aa45)

### 순간에 대한 시각화

[Making an Audio Waveform Visualizer with Vanilla JavaScript](https://css-tricks.com/making-an-audio-waveform-visualizer-with-vanilla-javascript/)

[react-audio-visualization](https://github.com/elliehoward/react-audio-visualization)

[mozilla AnalyserNode 예제](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getFloatFrequencyData#Drawing_a_spectrum)

### 총 길이에 대한 시각화

[wavesurfer-js](https://github.com/katspaugh/wavesurfer.js)

-   [examples](https://wavesurfer-js.org/examples/)
-   [Simple audio waveform with Wavesurfer.js and React](https://medium.com/trackstack/simple-audio-waveform-with-wavesurfer-js-and-react-ae6c0653b240)

-   이슈
    -   문제 : The AudioContext was not allowed to start
    ```javascript
       wavesurfer.on('ready', function () {
           wavesurfer.play()
       }
    ```
    -   관련 이슈 : https://github.com/katspaugh/wavesurfer.js/issues/1657
    -   결론 : 사용자 액션으로 play 하면 된다. 이유는 아직 모르겠다

## Custom

[Building a Custom HTML5 Audio Player With Javascript ](http://alexkatz.me/posts/building-a-custom-html5-audio-player-with-javascript/)

## TEST

### Not implemented: HTMLMediaElement.prototype.pause

[issue](https://github.com/jsdom/jsdom/issues/2155#issuecomment-366703395)

```
window.HTMLMediaElement.prototype.load = () => { /* do nothing */ };
window.HTMLMediaElement.prototype.play = () => { /* do nothing */ };
window.HTMLMediaElement.prototype.pause = () => { /* do nothing */ };
window.HTMLMediaElement.prototype.addTextTrack = () => { /* do nothing */ };
```
