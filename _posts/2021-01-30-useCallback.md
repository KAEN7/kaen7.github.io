---
title: useCallback
categories: [REACT]
comments: true
---

# useCallback이란?
이전에 만들었던 함수를 재사용  
함수를 감싸줘서 사용

- 예제
``` javascript
// useCallback 불러오기
import React, { useState, useRef, useMemo, useCallback } from 'react';
import CreateUser from './components/CreateUser';
import UserList from './components/UserList';
import './App.css';

function App() {
  const [inputs, setInputs] = useState({
    username: '',
    email: '',
  });
  const { username, email } = inputs;

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

  const onRemove = useCallback((id) => {
    setUsers(users.filter((user) => user.id !== id));
  }, [users]);

  const onToggle = useCallback((id) => {
    setUsers(users.map(
      (user) => user.id === id
        ? { ...user, active: !user.active }
        : user
    ));
  }, [users]);
}
export default App;
```