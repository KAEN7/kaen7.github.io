---
title: slide text
categories: [css]
comments: true
---

# slide text 만들기
css animation을 사용해서 위아래로 움직이는 슬라이드 텍스트를 구현

주석에 설명을 적어놓음

- html
    ``` html
    <!DOCTYPE html>
    <html lang="ko">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>슬라이딩 텍스트</title>
    </head>
    <body>
        <div class="slide__box"> <!-- 슬라이더를 감싸주는 박스 -->
            <!-- 슬라이더 목록 -->
            <div class="slide__text">First</div>
            <div class="slide__text">Second</div>
            <div class="slide__text">Thrid</div>
            <div class="slide__text">Last</div>
        </div>
    </body>
    </html>
    ```

- css
    ``` css
    body {
        margin: 0;
        padding: 0;
        font-family: montserrat, sans-serif;
        background: black;
    }

    .slide__box {
        color: #fff;
        position: absolute; /* 부모기준으로 위치하기 위해 사용 */
        top: 50%;
        background: #a09346;
        padding: 0 40px;
        width: 100%;
        height: 60px;
        overflow: hidden; /* 슬라이더가 하나씩만 보이도록 나머지는 숨겨줌 */
    }

    .slide__text {
        text-align: center;
        font-size: 40px;
        line-height: 60px;
    }

    /* 첫번째부터 시작되도록함 이걸 안하면 슬라이더들이 제각각 움직임 */
    .slide__text:first-child {
        animation: slide 12s infinite;
    }

    /* 진행률마다 적용되는 CSS 값을 넣어줌 */
    @keyframes slide {
        0% {
            margin-top: 0;
        }
        16% {
            margin-top: -60px;
        }
        33% {
            margin-top: -120px;
        }
        50% {
            margin-top: -180px;
        }
        66% {
            margin-top: -120px;
        }
        82% {
            margin-top: -60px;
        }
        100% {
            margin-top: 0;
        }
    }
    ```