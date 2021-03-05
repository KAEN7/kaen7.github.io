---
title: useReducer
categories: [REACT]
comments: true
---

# useReducer란?

useState와 같이 상태를 관리하는 Hook  
`컴포넌트 외부에서도 상태를 관리할 수 있음`

- 구조

  ```jsx
  import React, { useReducer } from "react";

  const [number, dispatch] = useReducer(reducer, initialState);
  ```

  - number = 현재 상태

  - dispatch
    액션을 발생시키는 함수

    ```jsx
    // 예시
    dispatch({
      type: "INCREMENT",
      diff: 4,
    });
    ```

  - reducer
    현재 상태와 액션 객체를 파라미터로 받아와서 새로운 상태를 반환해주는 함수

    - state: 현재 상태
    - action: 업데이트와 관련된 정보를 가진 객체
    - return: 업데이트될 값

    ```jsx
    // 예시

    // reducer
    function reducer(state, action) {
      // switch문으로 type 상태 업데이트 로직 구성
      switch (action.type) {
        case "INCREMENT":
          return state + 1;
        case "DECREMENT":
          return state - 1;
        default:
          return state;
      }
    }

    // action
    {
        type: 'SAMPLETYPE',
        explain: '타입값은 대문자 국룰',
        object: 'action은 주로 type값을 가진 객체 형태임'
    }
    ```

## useState or useReducer

둘다 상태를 관리하는 hook인데 어떤게 더 유용할까요?  
보통 useState는 단순한 값에 사용되고  
useReducer는 구조가 복잡할 때 사용됩니다
