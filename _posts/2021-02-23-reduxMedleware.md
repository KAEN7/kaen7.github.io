---
title: Redux medleware
categories: [REACT]
comments: true
---

# 리덕스 미들웨어란?

주로 비동기 작업을 처리할 때 사용 ex) API 요청

![리덕스 미들웨어](https://i.imgur.com/31tvphE.png)
미들웨어를 통해 액션이 디스패치 된 다음 리듀서에서 해당 액션을 받아와 업데이트하기 전에 추가적인 작업을 할 수 있음

추가적인 작업 목록

- 특정 조건에 따라 액션이 무시되게 할 수 있음
- 액션을 콘솔에 출력하거나 서버쪽에 로깅할 수 있음
- 액션이 디스패치 됬을 때 이를 수정해서 리듀서에게 전달할 수 있음
- 특정 액션이 발생했을 떄 이에 기반하여 다른 액션이 발생되도록 할 수 있음
- 특정 액션이 발생했을 때 특정 자바스크립트 함수를 실행시킬 수 있음

## 설치

```
yarn add redux react-redux
```

## 템플릿

```jsx
const middleware = (store) => (next) => (action) => {
  // 하고 싶은 작업...
};
```

- store
  리덕스 스토어 인스턴스이며 안에 `dispatch`, `getState`, `subscribe` 내장함수가 들어있음

- next
  액션을 다음 미들웨어에게 전달하는 함수, `next(action)`형태로 사용함  
   다음 미들웨어가 없다면 리듀서에게 액션을 전달해줌

- action
  현재 처리하고 있는 액션 객체

- 예시

  ```jsx
  const 미들웨어 = (store) => (next) => (action) => {
    console.log(action); // 액션 출력
    const result = next(acton); // 다음 미들웨어에게 액션 전달

    return result; // 반환되는 값은 dispatch(action)의 결과물이 됨
  };

  export default 미들웨어;
  ```

## 미들웨어 적용

스토어에 미들웨어를 적용할 때는 `applyMiddleware`함수를 사용해서 적용

```jsx
const store = createStore(rootReducer, applyMiddleware(미들웨어이름));
```
