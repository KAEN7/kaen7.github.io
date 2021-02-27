---
title: redux-thunk
categories: [REACT]
comments: true
---

# redux-thunk란?

리덕스에서 비동기 작업을 처리할 때 가장 많이 사용하는 미들웨어이며 이것을 통해 액션 객체가 아닌 함수를 디스패치 할 수 있음

redux-thunk라는 미들웨어는 API 호출이 필요할 때만 사용됨

함수를 디스패치할 때는 해당 함수에서 `dispatch`와 `getState`를 파라미터로 받아와야하는데 이 함수를 만들어주는 함수를 `thunk`라고 함
