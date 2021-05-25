# Array.isArray()

`Array.isArray()` 메서드는 인자가 `Array` 인지 판별합니다

구문

```jsx
Array.isArray(obj)
```

```jsx
Array.isArray([1, 2, 3]);  // true
Array.isArray({foo: 123}); // false
Array.isArray('foobar');   // false
Array.isArray(undefined);  // false
```