# Next/image가 외부 이미지를 import 해오지 못하는 문제

lostgold 페이지 작업중에 OpenAPI에서 받아온 외부 이미지를 Next/Image src에 지정해줬더니 다음과 같은 에러가 발생했다

```
On one of your pages that leverages the next/image component, you passed a src value that uses a hostname in the URL that isn't defined in the images.domains config in next.config.js.
```

src에 들어가는 도메인을 next.config.js에 미리 정의해줘야 한다고 한다.
다음과 같은 방법으로 해결했다.

## 해결방법

우선 next.config.js 파일에 들어가서 다음과 같이 domains를 정의해주었다

```
const nextConfig = {
  images: {
    domains: ["localhost", "*"]
  },
}
```

그리고 src를 넣어줬던 Image 코드에 찾아가보자

```
<Image
  src={CharacterImage}
  width="223.73"
  height="258.81"
  alt={"profile"}
  unoptimized={true}
/>
```

`unoptimized`를 주면 이미지 최적화가 이루어지지 않는 단점이 있지만 해당 에러는 해결되게 된다

## 정리

next.config.js와 Image 코드를 간단하게 건드리면 해결되는 에러이지만
unoptimized를 적용해서 자동 이미지 최적화가 되지 않는다는 단점은 문제가 될 수 있을 것 같다

해당 문제를 해결할 방법을 리서치할 필요가 있어보인다
