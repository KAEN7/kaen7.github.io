---
title : "React"
category :
    - React
tag :
    - React
toc : true
---

# 리액트 기본

### 리액트 불러오기
리액트 최상단에 사용

``` react
import React from 'react';
```

### 리액트 내보내기
리액트 최하단에 사용

```
export default 컴포넌트이름;
```

### 컴포넌트
- 일종의 UI조각
- 쉽게 재사용가능

### reactDOM
- 리액트를 웹사이트에 출력(render)하는걸 도와주는 모델
    - 리액트를 웹사이트에 올리고싶다 => reactDOM
    - 리액트를 모바일 앱에 올리고싶다 => reactNavie
- ReactDom.render
    - 브라우저에 있는 실제 DOM 내부에 리액트 컴포넌트를 렌더링하겠다는 것을 의미

### JSX
- 리액트에서 생김새를 정의할 때 사용하는 문법
- HTML같이 생겼지만 실제로는 Javascript

``` react
return <div>안녕하세요!</div>
```

- 태그는 꼭 닫혀있어야함
- Fragment
    - JSX는 꼭 닫혀있는 태그로 감싸져 있어야하기 때문에 빈태그로 껍데기를 만들어줌

``` react
function App() {
    return (
        <>  // Fragment
            <Hello />
            <div>하윙</div>
        </>
    )
}
```

- JSX 안에 자바스크립트 값 사용
    - JSX 내부에 자바스크립트 변수를 보여줘야할 때는 {}로 감싸서 보여줌

``` react
import React from 'react';
import Test from './Test';

function App() {
    const name = 'react';
    return (
        <>
            <Test />
            <div>{name}</div>
        </>
    )
}

export default App;
```

- style과 className
    - JSX에서 태그에 style과 class 설정하는 법은 HTML과는 다름
    - 인라인 스타일은 객체 형태로 작성해야함
    - background-color처럼 -로 구분되는 것은 camelCase 형태로 바꿔줘야함

``` react
import React from 'react';
import Test from './Test';

function App() {
    const name = 'react';
    const style = {
        backgroundColor = 'black',
        color: 'blue',
        fontSize: 20,
        padding: '15px'
    }

    retrun(
        <>
            <Test />
            <div className="testName" style={style}>{name}</div>
        </>
    )
}

export default App;
```