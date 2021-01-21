---
title: react-router-dom
categories: [REACT]
comments: true
---

# react-router-dom이란?
페이지를 이동할때 react-router-dom이란 것을 이용한다

- router 적용
    라우터를 사용하기 위해선 최상위 컴포넌트를 묶고 시작해야함

    ``` javascript
    import React from 'react';
    import App from './App';
    import { BrowserRouter } from 'react-router-dom';
    
    function Root() {
        return (
            <BrowserRouter>
                <App />
            </BrowserRouter>
        )
    }

    export default Root;
    ```

- react-router-dom 패키지
    |패키지|사용처|
    |-|-|-|
    |react-router|웹 && 앱|
    |react-router-dom|웹|
    |react-router-native|앱|
    
- 설치방법  
    react-router-dom을 기준으로 작성되었습니다
    
    npm에서 설치
    ```
    npm i react-router-dom
    ```

    import 시키기
    ``` javascript
    import { BrowserRouter,Route, Link, Switch } from "react-router-dom";
    ```

    import된 4가지들은 각각  
    
    |router|mean|
    |-|-|
    |BrowerRouter|history API를 사용해 URL과 UI를 동기화하는 라우터|
    |Route|컴포넌트의 속성에 설정된 URL과 현재 경로가 일치하면 해당하는 컴포넌트, 함수를 렌더링|
    |Link|HTML에 'a'태그와 비슷하며 to속성에 설정된 링크로 이동함(href와 유사).<br>history 스택에 저장됨|
    |Switch|자식 컴포넌트 Route 또는 Redirect 중 매치되는 첫번째 요소를 랜더링.<br>Switch를 사용하면 BrowerRouter만 사용할 때와는 다르게 하나의 매칭되는 요소만 랜더링한다는 점을 보장해줌.<br>사용하지 않을 경우 매칭되는 모두를 랜더링함|