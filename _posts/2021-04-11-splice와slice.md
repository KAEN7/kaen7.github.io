---
title: splice와 slice
categories: [JavaScript]
comments: true
---

# splice()

배열에서 특정항목을 제거할때 사용

```javascript
const numbers = [10, 20, 30, 40, 50];
const num = numbers.indexOf(30);
console.log(num); // 2
```

`indexOf`로 원하는 숫자를 선택해서 몇번째인지 알수도 있지만 splice가 더 편한 점이 있어서 알아보겠습니다

> splice(index, count)

    index째부터 count개수만큼 제거할 것이다

    ```javascript
    numbers.splice(num, 3);
    console.log(numbers); // [10, 20]
    ```

    기존 배열에서 해당하는 값을 빼와서 새로운 배열을 만드는 형태이다.

# slice()

splice와 유사하지만 차이점이 있다  
start부터 end바로 전 순번까지를 의미

> slice(start, end)

    ```javascript
    const numbers = [10, 20, 30, 40, 50];
    const sliced = numbers.slice(0, 2);

    console.log(sliced); // [10, 20];
    ```

    slice는 splice와 다르게 기존 배열을 건드리지 않는다
