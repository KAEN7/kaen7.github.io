---
title: createElement
categories: [REACT]
comments: true
---

# createElement란?

`React.createElement(type, [props], [...children])`이라는 API를 통해 컴포넌트를 생성할 수 있다

예시로 보면 파라미터가 무엇을 뜻하는지 쉽게 알 수 있다

```jsx
const props = { className: "kaen", onClick: () => {} };
const child = <h2>Hello</h2>;

React.createElement(div, props, child);
```

이 예시가 적용되면

```html
<div>
  <h2>Hello</h2>
</div>
```

가 되게 된다
