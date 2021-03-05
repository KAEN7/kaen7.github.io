---
title: Context API
categories: [REACT]
comments: true
---

# Context API란?

컴포넌트 상관없이 전역적으로 특정 값을 사용할 때 쓰임

- 주로 애플리케이션에 전역적으로 데이터가 사용되야 할 때 쓰임
- 리덕스, 리액트 라우터, 스타일 컴포넌트 등의 라이브러리가 이 기술을 기반으로 구현됨
- 사용자 로그인 정보, 애플리케이션 환경 설정, 테마 등을 관리할 때 사용됨

## 사용법

- createContext

  새 context를 만들때 사용, 인자로 기본값을 줌

  ```jsx
  import { createContext } from "react";

  const NewSample = createContext(false);
  ```

- useContext
  context 조회할 때 사용

  ```jsx
  import { useContext } from "react";

  /* 최종 전달할 컴포넌트 */
  function Child() {
    /* 위에서 만든 NewSample 변수를 가져와서 새로운 변수에 넣어줌 */
    const ChildContext = useContext(NewContext);

    /* 새로 만든 변수를 사용함 */
    return <div>Im {ChildeContext}</div>;
  }
  ```

- Provider
  Provider로 감싸서 전역 값을 줄 수 있음

  ```jsx
  // value로 blueSea를 전달한 예시
  return (
    <SampleText.Provider value={blueSea}>
      <Childeren />
    </SampleText.Provider>
  );
  ```

  value 값에는 상태 값 뿐만 아니라 함수도 전달할 수 있음

- 예시
  ``` jsx
  import React, { createContext, useContext} from 'react';

  // 2. 새로운 context를 만들어줌
  const FlowerColor = createContext('invisible');

  function Flower() {
    // 3. 만들어준 context를 새로운 함수에 호출시킴
    const RealColor = useContext(FlowerColor);
    return (
      <div>{RealColor} 루나리아</div> // 하얀 루나리아
    )
  }

  function Sample() {
    return (
      // 1. value 값인 '하얀'이 전달
      <Color.Provider value={하얀}>
        <Flower />
      </Color.Provider>
    )
  }
  ```