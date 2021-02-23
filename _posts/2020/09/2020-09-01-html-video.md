---
title: 'html video'
---

## 문서

[HTMLMediaElement mozilla](https://developer.mozilla.org/ko/docs/Web/API/HTMLMediaElement)

[MediaDevices.getUserMedia()](https://developer.mozilla.org/ko/docs/Web/API/MediaDevices/getUserMedia)

-   미디어 입력 장치 사용 권한을 요청하며, 사용자가 수락하면 요청한 미디어 종류의 트랙을 포함한 MediaStream을 반환합니다
-   IE 지원 안 함

## blog

[Capture Audio and Video in HTML5](https://www.html5rocks.com/ko/tutorials/getusermedia/intro/)

-   소개하는 글
-   getUserMedia()로 가는 길
-   시작하기
-   사진 찍기
-   Applying Effects
-   Web Audio API와 함께 getUserMedia 사용하기
-   결론
-   Additional resources

[Validating Video Uploads On The Frontend](https://brettdewoody.com/video-dimensions-on-the-frontend/)

[[번역] iOS를 위한 새로운 <video> 정책](https://d0gf00t.tistory.com/35)

## Event

[seeked event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeked_event)

[seeking event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seeking_event)

## Method

[fastSeek](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/fastSeek)

## Example

[Example Playlist Files for use with HTTP Live Streaming](https://developer.apple.com/library/archive/technotes/tn2288/_index.html#//apple_ref/doc/uid/DTS40012238-CH1-I_FRAME_PLAYLIST)

[Video player styling basics](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Video_player_styling_basics)

[Building Custom Controls for HTML5 Videos](https://blog.teamtreehouse.com/building-custom-controls-for-html5-videos)

[Video 에서 지정된 시간의 thumbnail 가져 오기](https://usefulangle.com/post/46/javascript-get-video-thumbnail-image-jpeg-png)

## After Effects

[lottie-web](https://github.com/airbnb/lottie-web)

-   Lottie is a mobile library for Web, and iOS that parses Adobe After Effects animations exported as json with Bodymovin and renders them natively on mobile!
-   promo 에서 사용

[lottie example](https://lottiefiles.com/web-player?lottie_url=https%3A%2F%2Fassets1.lottiefiles.com%2Fprivate_files%2Flf30_amtyctks.json)

```html
<script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
<lottie-player src="https://assets1.lottiefiles.com/private_files/lf30_amtyctks.json" background="transparent" speed="1" style="width: 300px; height: 300px;" loop controls autoplay></lottie-player>
```

[Bodymovin - Export After Effects animations to HTML5](https://www.creativebloq.com/how-to/export-after-effects-animations-to-html5)

[Adobe After Effects 사용 안내서 > 표현식 및 자동화](https://helpx.adobe.com/kr/after-effects/using/expression-language-reference.html#%ED%91%9C%ED%98%84%EC%8B%9DJavaScript%EC%97%94%EC%A7%84)

## 이슈

### 여려개 video tag 사용

1. [video not playing in chrome unless developer tools window open](https://stackoverflow.com/questions/43570460/html5-video-autoplay-on-iphone)
2. [HTML5 Video autoplay on iPhone](https://stackoverflow.com/questions/51083662/video-not-playing-in-chrome-unless-developer-tools-window-open)

#### 결론

muted 적용 추가

### 자동 재생이 가능한 경우

[참고](https://okayoon.tistory.com/entry/video%ED%83%9C%EA%B7%B8-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%9D%B4%EC%8A%88-%EC%A0%95%EB%A6%AC-%EC%82%AC%ED%95%AD)

1. 이벤트 (click 등) 발생 시
2. 비디오 내에 오디오 트랙이 없는 경우
3. muted 속성 적용
4. iphone 에서 playsinline 요소 추가
5. 모바일일 때 해당 사이트를 즐겨찾기 한 경우
6. 부모 frame 에게 자식 frame 에게 비디오 권한을 부여한경우

### Property 'playsinline' does not exist on type 'DetailedHTMLProps<VideoHTMLAttributes<HTMLVideoElement>, HTMLVideoElement>'.

#### 결론

typescript 은 cammelCase 을 사용한다

그래서 playsInline 으로 사용하면 된다
