---
title: useCallback
categories: [REACT]
comments: true
---

# useCallback이란?
최적화하는데 사용되는 Hook으로써 이전에 만들었던 함수를 재사용  
즉, useCallback에 두 번째 인자 배열 내부에 존재하는 인덱스들을 바라보고 값이 변경되었을 때, 해당 함수는 다시 그려짐

- 구조
  ``` jsx
  const memoizedCallback = useCallback(
    () => {
      doSomething(a, b);
    },
    [a, b],
  );
  ```

- 예제
  ``` jsx
  // useCallback 불러오기
  import React, { useState, useRef, useMemo, useCallback } from 'react';
  import CreateUser from './components/CreateUser';
  import UserList from './components/UserList';
  import './App.css';

  function App() {
    // useCallback으로 감싸줌
    const onChange = useCallback((e) => {
      const { name, value } = e.target;
      setInputs({
        ...inputs,
        [name]: value
      });
    }, [inputs]); {/* onChange함수에서 의존되고 있는 값인 inputs를 Deps로 넣어줌 */}

    // useCallback으로 감싸줌
    const onCreate = useCallback(() => {
      const user = {
        id: nextId.current,
        username,
        email,
      };
      setUsers([...users, user]);
      setInputs({
        username: '',
        email: ''
      });
      nextId.current += 1;
    }, [username, email, users]); {/* 의존되는 값들을 Deps에 넣어줌 */}    
  }

  export default App;
  ```