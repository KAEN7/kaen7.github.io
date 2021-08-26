# React에서 로컬 video태그 사용법

```jsx
// 로컬파일을 불러온 후
import video from "../img/mainpage.mp4";

// 아래와 같이 사용 하면 끝
<video className="video" autoPlay muted loop>
  <source src={video} type="video/mp4"></source>
</video>
```