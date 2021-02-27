---
title: redux-logger
categories: [REACT]
comments: true
---

# redux-logger란?

redux의 상태를 로그로 보여주는 모듈로써 로그를 관리 및 로그보기

- 설치

  ```
  yarn add redux-logger
  ```

- 예시

  ```jsx
  // createLogger로 불러오기
  import { createLogger applyMiddleware } from "redux-logger";

  // 여러개의 미들웨어 적용
  const logger = createLogger();
  const store = createStore(rootReducer, applyMiddleware(미들웨어, logger));
  ```
