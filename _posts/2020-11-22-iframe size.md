---
title : "iframe 가로세로 비율"
category :
    - CSS
tag :
    - CSS
toc : true
---

# iframe 감싸주기

유튜브에서 iframe을 가져오면 사이즈가 정해져있는데 
반응형 웹에서 사용하기위해 자동 조절을 하려면
iframe을 감싸주는 div를 만들면 된다

``` html
<div> class="playVideo">
        <iframe width="1280" height="720" src="https://www.youtube.com/embed/XRnJUs8EDfs" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
```

# css 건드리기

감싸준 div의 크기를 정해준다

``` css
.playVideo {
    position: relative;
    width: 100%;
    height: 56.25%;
}

.playVideo iframe {
    position: absolute;
    width: 100%;
    height: 100%;
}
```

.playVideo의 height를 56.25처럼 애매하게 주는 이유는 영화비율인 16:9 비율로 맞추기 위함임
