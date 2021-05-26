# Object.values()

`Object.values()` 메서드는 속성의 값들로 이루어진 배열을 리턴합니다.

`for ...in` 구문과 동일한 순서를 가집니다

```jsx
const obj = {
  name: 'kaen',
  age: 26,
  dead: false
};

console.log(Object.values(obj)); // Array ["kaen", 26, false]
```