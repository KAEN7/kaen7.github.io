# 환경변수 (process.env)

## 환경 변수란?

어느 환경에 배포하느냐에 따라서 다르게 설정해야하는 항목은 보통 운영 체제 레벨에서 환경 변수를 통해 관리하게 됩니다

개발 환경에서는 로컬 DB를 사용해야하는데, 운영 환경에서는 원격 DB를 사용해야하는 경우를 들 수 있습니다. 

뿐만 아니라 DB password나 API key와 같은 인증 정보는 공개된 코드 저장소에 올리면 안 되기 때문에 환경 변수로 저장해놓고 사용하는 것이 일반적입니다.

## 환경 변수 접근

Node.js에서 환경변수에 접글할 때는 `process.env` 라는 내장 자바스크립트 객체를 통해 접근합니다

`process` 는 전역 객체에서 별도로 import 해야되는 모듈이 없으므로 어디서든 접근이 가능합니다

```jsx
> process.env.API_KEY
'abc'
> process.env.DB_PASSWORD
'1234'
```

## 자유로운 가변 객체

`process.env` 는 가변 객체이기 때문에 기존에 설정된 값을 자유롭게 갱신 또는 제거할 수 있습니다

```jsx
> process.env.API_KEY = "abc"
'abc'
> process.env.API_KEY
'abc'
> process.env.API_KEY = "def"
'def'
> process.env.API_KEY
'def'
'1234'
> delete process.env.API_KEY
true
> process.env.API_KEY
undefined
```

## 참조

[Node.js에서 환경 변수 다루기 (process.env)](https://www.daleseo.com/js-node-process-env/)