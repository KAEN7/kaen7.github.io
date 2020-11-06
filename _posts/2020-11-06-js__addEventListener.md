---
title : "addEventListner"
category :
    - JavaScript
tag :
    - JavaScript
toc : true
---

# addEventListner()
addEventListner() 메서드는 지정한 이벤트가 발생할때 설정한 함수를 호출

## 문법
```
document.addEventListener(event, function, sueCapture);
```

**event** : 반응할 이벤트 유형
**function** : 이벤트가 발생할 때 실행할 함수
**useCapture** : eventTarget으로 전송하기 전, 등록된 function으로 타입의 이벤트 전송여부를 나타내는 불린값 ( 생략 가능 )