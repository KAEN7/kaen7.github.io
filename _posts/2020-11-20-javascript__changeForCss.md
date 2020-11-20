---
title : "자바스크립트에서 CSS 바꾸기"
category :
    - JAVASCRIPT
tag :
    - JAVASCRIPT, CSS
toc : true
---

# JAVASCRIPT
1. 변수에서 태그를 받아오기

``` javascript
const display = document.getElementById('ID');
```
2. style 속성에 원하는 값을 넣어주기

``` javacript
display.style.backgroundColor = 'black';
```

## 예시
``` javascript
const change = document.getElementById('btn');
const formChange = document.querySelector('search-bar');
const searchBtn = document.getElementById('btn');
const main = document.getElementById('main');
const naver = document.getElementById('naver');
const google = document.getElementById('google');

function changeSearch() {
    if(btn.innerText === 'G') {
        btn.innerText = 'N';
        main.style.backgroundColor = 'green';     
        google.style.display = 'none';
        naver.style.display = 'block';
    } else {
        btn.innerText = 'G';
        main.style.backgroundColor = 'white';
        google.style.display = 'block';
        naver.style.display = 'none';
    }
}

if(change) {
    change.addEventListener('click', changeSearch);
}
```