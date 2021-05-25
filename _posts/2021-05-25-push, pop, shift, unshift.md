# push, pop, shift, unshift

# push(): 배열 끝에 항목을 추가합니다.

```jsx
const arr = [1,2,3,4,5,6,7];

arr.push(30); // 8

console.log(arr);
// (8) [1, 2, 3, 4, 5, 6, 7, 30]
```

# pop(): 배열 끝에서 항목을 제거합니다.

```jsx
const arr = [1,2,3,4,5,6,7];

arr.pop(); // 7
console.log(arr); // [1,2,3,4,5,6]
```

# shift(): 배열의 시작 부분에서 항목을 제거합니다.

```jsx
const arr = [1,2,3,4,5,6,7];
arr.shift(); // 1
console.log(arr); // (6) [2, 3, 4, 5, 6, 7]
```

# unshift(): 배열 시작 부분에 항목 추가

```jsx
const arr = [1,2,3,4,5,6,7];
arr.unshift(); // 7
console.log(arr); // (7) [1, 2, 3, 4, 5, 6, 7]
```