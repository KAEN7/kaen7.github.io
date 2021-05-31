# Object.assign()

`Object.assign()` 함수는 여러 개의 매개변수 객체중 target 매개변수 객체에 나머지 객체를 병합하는 함수입니다

```jsx
Object.assign(target, 객체여러개)
```

```jsx
const obj1 = {a:1};
const obj2 = {b:2};
const obj3 = {c:3};

const obj = Object.assign({}, obj1, obj2, obj3);
console.log(obj); // {a: 1, b: 2, c: 3}
```