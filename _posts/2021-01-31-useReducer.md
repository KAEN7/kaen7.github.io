---
title: useReducer
categories: [REACT]
comments: true
---

# useReducer란?
useState와 같이 상태를 관리하는 훅 중 하나  
특징으로는 컴포넌트 바깥에서 해당 상태를 관리할 수 있음


- useReducer 구조
    ``` jsx
    const [number, dispatch] = useReducer(reducer, 기본값);
    ```
    - number = 현재 상태
    - dispatch
        액션을 발생시키는 함수
        ``` javascript
        dispatch({
            type: 'INCREMENT',
            diff: 4
        })
        ```
    - reducer: 상태를 업데이트하는 함수
        ``` jsx
        function reducer(state, action) {
            switch(action.type) {
                case 'INCREMENT':
                    return state + 1;
                case 'DECREMENT':
                    return state - 1;
                default:
                    return state;
            }
        }
        ```