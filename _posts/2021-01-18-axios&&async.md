---
title: axios, async
categories: [REACT]
comments: true
---

# axios란?
fetch의 업그레이드 기능  
바닐라 자바스크립트로 구현된 비동기 통신 라이브러리(API에서 데이터를 받아옴)

- 설치방법
    ```
    npm install axios
    ```

- axios로 api 데이터 가져오기
    ``` javascript
    getMovies = () => {
        const movies = axios.get("https://yts-proxy.now.sh/list_movies.json");
    }
    ```
    axios.get으로 해당 url안에 json을 읽어올수있음, 그러나 시간이 좀 걸림

# async란?
우선 async와 await은 한쌍이다

- async로 데이터 가져오기
    ``` javascript
    getMovies = async () => {
    const movies = await axios.get("https://yts-proxy.now.sh/list_movies.json");
    }
    ```

    async와 await을 통해 우리는 '해당 작업이 끝날때까지 기다려!'라고 명령을 전달할 수 있다