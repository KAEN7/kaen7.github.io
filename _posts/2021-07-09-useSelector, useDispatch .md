# useSelector, useDispatch

리덕스 스토어와 연동된 컨테이너 컴포넌트를 만들때 사용

`useSelector` 는 상태 조회

`useDispatch` 는 액션 생성

```jsx
import React from 'react'
import Counter from '../components/Counter'
import { increase, decrease } from '../modules/counter'

import { useSelector, useDispatch } from 'react-redux'

const CounterContainer = () => {
		// counter에 있는 number 값 가져오기 즉 store에 저장된 state를 가져오기
    const number = useSelector(state => state.counter.number)
	
		// 변수에 담아서 dispatch를 날림
    const dispatch = useDispatch()

    return <Counter number={number} onIncrease={dispatch(increase())} onDecrease={dispatch(decrease)} />
}

export default CounterContainer
```