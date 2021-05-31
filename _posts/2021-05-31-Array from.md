# Array.from

`Array.from()` 은 배열을 초기화하는 함수입니다

```jsx
Array.from('Tei'); // ['T', 'e', 'i']

const arr = ['ab', '12']
Array.from(arr); // (2) ["ab", "12"]

Array.from([1, 2, 3], x => x+x); // [2, 4, 6]
```