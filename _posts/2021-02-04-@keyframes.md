---
title: @keyframes
categories: [css]
comments: true
---

# @keyframes란?
css animation 속성중 하나  
styled-component 안에 이미 내장되어 있음

- transition: 단순한 엘리먼트 상태변화에 쓰임
- animation: 다이나믹한 효과를 주는데 쓰임

0~100%구간까지 변화되는 CSS 값을 정의하고 애니메이션이 적용되는 요소에 이를 적용하는 방식

- 예제  
    ``` css
    .line:first-child {
        animation: anim 12s infinite;
    }

    @keyframes anim {
        0% {
            margin-top: 0;
            opacity: 0;
        }
        16% {
            margin-top: -60px;
            opacity: 1;
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