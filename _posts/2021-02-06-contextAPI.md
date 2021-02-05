---
title: Context API
categories: [REACT]
comments: true
---

# Context API란?
- 주로 애플리케이션에 전역적으로 데이터가 사용되야 할 때 쓰임  
- 리덕스, 리액트 라우터, 스타일 컴포넌트 등의 라이브러리가 이 기술을 기반으로 구현됨
- 사용자 로그인 정보, 애플리케이션 환경 설정, 테마 등을 관리할 때 사용됨

## createContext
---
새 컨텍스트를 만들때 쓰는 함수
``` jsx
import { createContext } from 'react';
```

## Provider
- Provider를 사용해서 전역 값인 value를 줄 수 있음(value 값을 꼭 줘야함)

``` jsx
return (
    <SampleText.Provider value={blueSea}>
        <Childeren />
    </SampleText.Provider>
)
```

value 값에는 상태 값 뿐만 아니라 함수도 전달할 수 있음