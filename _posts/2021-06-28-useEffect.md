# useEffect

`useEffect` 는 컴포넌트 내에서 `Side Effect` 를 실행할 수 있게 하는 `Hook` 입니다

```jsx
useEffect(함수, [종속성1, 종속성2, ...])
```

배열 내의 어떤 값이 변할때만 effect가 발생하는 함수가 실행이 됩니다

즉 `useEffect` 는 렌더링, 혹은 변수의 값 혹은 오브젝트가 달라지게 되면 그것을 인지하고 업데이트해주는 함수입니다

```jsx
// 빈배열 넣기
useEffect(함수, []); // 처음 컴포넌트가 생성될때만 실행됨

// 아무것도 넣지 않기
useEffect(함수); // 컴포넌트가 처음 생성되거나, props가 업데이트되거나, 상태가 업데이트될 때 함수가 실행됨
```

[두 방식의 차이점](https://www.notion.so/9722eb8b04dd44e8a0feea6a68b10581)

## 참조

[React Hooks : useEffect() 함수](https://xiubindev.tistory.com/100?category=826117)