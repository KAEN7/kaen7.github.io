# AXIOS와 FETCH의 차이점

### Axios

### 장점

- response timeout 처리 방법이 있다. (fetch에는 존재하지 않는 기능)
- promise 기반으로 다루기가 쉽다
- **크로스 브라우징이 좋아 브라우저 호환성이 뛰어나다.**

### 단점

- 모듈 설치 필요.

### fetch

### 장점

- 내장 라이브러리이기에 별도의 import를 해줄 필요가 없다.
- promise 기반으로 다루기가 쉽다.
- **내장 라이브러리이기에 사용하는 프레임워크가 안정적이지 않을 때 사용하기 좋다.**

### 단점

- internet explorer의 경우에는 fetch를 지원하지 않는 버전도 존재한다. (브라우저 호환성이 상대적으로 떨어진다.)
- 기능이 부족하다.

## 참조

[[개발상식] Ajax와 Axios 그리고 fetch](https://velog.io/@kysung95/%EA%B0%9C%EB%B0%9C%EC%83%81%EC%8B%9D-Ajax%EC%99%80-Axios-%EA%B7%B8%EB%A6%AC%EA%B3%A0-fetch)