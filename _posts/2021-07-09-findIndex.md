# findIndex

`findIndex()` 판별 함수를 만족하는 배열의 첫번째 요소의 인덱스를 반환하는 메소드입니다

만족하는게 없으면 -1을 반환합니다

```jsx
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// expected output: 3
```