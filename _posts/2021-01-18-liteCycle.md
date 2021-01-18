---
title: life cycle
categories: [REACT]
comments: true
---

# life cycle
리액트 컴포넌트에는 생명주기가 존재하는데 쉽게 말하면 '실행순서'이다

![출처:https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/](/githubpage\assets\img\react_life_cycle.png)

``` javascript
componentDidMount() { // 랜더링 이후 즉시 호출되는 함수
    console.log('Componenet rendered');
}

componentDidUpdate() { // 랜더링이 완료된 직후에 호출
    console.log('I just updated');
}

componentWillUnmount() { // 컴포넌트가 사라지기전에 호출
    console.log('Goodbye, curel world');
}
```