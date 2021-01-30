---
title: useEffect
categories: [REACT]
comments: true
---

# useEffect란?
React 컴포넌트가 처음 화면에 나타나거나 사라질 때 어떤 특정 작업을 할 수 있으며  
컴포넌트의 어떤 프롭스나 상태가 변경되서 업데이트 되거나, 업데이트 되기 전에 어떤 작업을 할 수 있음

컴포넌트가 나타나는게 mount, 사라지는게 unmount

- 파라미터
    ``` javascript
    useEffect(() => , deps)
    ```
    첫번째 파라미터로는 함수를, 두번째는 Deps(함수)를 넣어줌  
    Deps는 의존되는 값을 넣어주는 것인데 의존되는 값이 비어있으면 컴포넌트가 처음 화면에 나타날 때만 실행됨

- 예제
    ``` javascript
    import React, { useEffect } from 'react';

    function User({ user, onRemove, onToggle }) {
        const { username, email, id, active } = user;
        // useEffect mount
        useEffect(() => {
            // props -> state
            // REST API
            // D3 Video.js
            // setInterval, setTimeout
            console.log('user 값이 설정됨');
            console.log(user);
            // useEffect unmount
            return () => {
                // clearInterval, clearTimeout
                // 라이브러리 인스턴스 제거
                console.log('user가 바뀌기전임!');
                console.log(user);
            };
        }, [user]);
    ```