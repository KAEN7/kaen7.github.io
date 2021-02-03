---
title: 자바스크립트에서 CSS 바꾸기
categories: [JavaScript]
comments: true
---

# 자바스크립트에서 CSS 바꾸기
1. 변수에서 태그를 받아오기

    ``` javascript
    const display = document.getElementById('ID');
    ```
2. style 속성에 원하는 값을 넣어주기

    ``` javacript
    display.style.backgroundColor = 'black';
    ```

- 예시
    ``` javascript
    const main = document.getElementById('main');
    const naver = document.getElementById('naver');
    const google = document.getElementById('google');

    function changeSearch() {
        if(btn.innerText === 'G') {
            main.style.backgroundColor = 'green';     
            google.style.display = 'none';
            naver.style.display = 'block';
        } else {
            main.style.backgroundColor = 'white';
            google.style.display = 'block';
            naver.style.display = 'none';
        }
    }
    ```
    id 값을 상수로 받아와서 `상수.style.css명령어`로 값을 매겨줌