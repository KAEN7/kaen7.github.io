---
title: useEffect
categories: [REACT]
comments: true
---

# useEffect란?

컴포넌트가 렌더링 될 때마다 특정 작업을 실행할 수 있도록 하는 Hook으로써
클래스 컴포넌트에서 사용되던 생명주기 메소드를 함수형에서도 사용할 수 있게하는 Hook

- 사용법

  ```jsx
  // useEffect 불러오기
  import React, { useEffect } from 'react';

  // 기본 형태
  useEffect(() => , deps) // deps는 배열 형태이며 의존값이나 빈 배열을 넣음
  ```

## 컴포넌트가 mount 됐을 때(처음 나타났을 때)

컴포넌트가 화면에 가장 처음 렌더링 될 때만 실행하고 싶으면 deps 위치에 빈 배열을 넣음

```jsx
useEffect(() => {
  console.log("처음 렌더링 될 때 실행됨");
}, []);
```

배열을 생략하면 리렌더링 될 때마다 실행됨

```jsx
useEffect(() => {
  console.log("렌더링 될 때마다 실행됨");
});
```

## 컴포넌트가 update될 때(특정 props, state가 바뀔 때)

특정값이 업데이트 될 때마다 실행하고 싶으면 deps 위치의 배열 안에 의존값을 넣어준다  
업데이트 될 때만 실행되는 것이 아닌 마운트 될 때도 실행된다

- 업데이트 될 때만 특정 함수를 실행하는 방법

  ```jsx
  const mounted = useRef(false); // 기본값을 false로

  useEffect(() => {
      // 기본값이 false이므로 mounted.current가 바뀌지 않는 이상 마운트될때 실행되지 않음
      if(!mounted.current) {
          mounted.current = true;
      } else {
          // any code
      }
  }, [바뀌는 값]);
  ```

## 컴포넌트가 unmount 될 때(사라질 때) && update 되기 직전에

return 뒤에 코드를 작성해주면 unmount될 때 사용됨

```jsx
useEffect(() => {
  console.log("noting");
  return console.log("umount");
}, []); // 빈 배열을 넣으면 unmount 될 때만 실행됨
```

[출처](https://xiubindev.tistory.com/100?category=826117)
