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
- 쉽게 재사용가능한 일종의 UI조각
- 컴포넌트의 이름 앞글자는 대문자

```
import React from 'react';

function Component(prop) {
    return <div>{props.name}</div>
}
```

### reactDOM
- 리액트를 웹사이트에 출력(render)하는걸 도와주는 모델
    - 리액트를 웹사이트에 올리고싶다 => reactDOM
    - 리액트를 모바일 앱에 올리고싶다 => reactNavie
- ReactDom.render
    - 브라우저에 있는 실제 DOM 내부에 리액트 컴포넌트를 렌더링하겠다는 것을 의미

### JSX
- 리액트에서 생김새를 정의할 때 사용하는 문법
- BABEL을 이용해서 XML 형태의 코드가 javascript로 변환됨
- HTML같이 생겼지만 실제로는 Javascript

``` react
return <div>안녕하세요!</div>
```

- 태그는 꼭 닫혀있어야함
- 2개 이상의 태그는 하나 이상의 태그로 감싸줘야 오류가 나지 않음
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

- 자바스크립트 변수를 사용할 때는 {}로 사용

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
- JSX에서는 class 지정자를 className이라고 적음
- style을 지정해주고 싶다면 style을 위한 객체를 만들어서 적용

``` 
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

- 스타일링크는 아래와 같이 표기

```
import "./style.css"
```

### props
- 상위 컴포넌트에서 하위 컴포넌트로 데이터를 전달하는 수단

``` react
// App.js
import React from 'react';
import Test from './Test';

function App() {
    return (
        <>
            <Test name='kaen'>  // kaen이란 props를 Test.js로 전달
        </>
    )
}

export default App;

// Test.js
import React from 'react';

function Test(props) {
    console.log(props)
    return (
        <>
            My name is {props.name}!  // My name is kaen!
        </>
    )
}

export default Test
```

- 매번 props. 라고 작성하기 싫으면 비구조화 할당(구조분해 할당)으로 인자를 전달해주면 됨

```
function Test({name, age}) {
    return <> {age} </>
}
```

- defaultProps로 기본값을 설정할 수 있음

```
import React from 'react';

function Test(props) {
    return
        <div>
            {props.name}의 Blog
        </div>
}

Test.defaultProps = {
    name: '사용자'
}

export default Test;
```

- children props를 사용해서 해당 컴포넌트 하위에 위치한 컴포넌트들을 불러올 수 있음

```
// App.js
import React from 'react';
import Test from './Test';

function App() {
    retrun <Test>하위!</Test>
}

export default react;

// Test.js
import React from 'react';

function Test(props) {
    return <div>오! {props.children}</div> // 오! 하위!
}

export default Test
```