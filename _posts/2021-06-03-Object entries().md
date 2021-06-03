# Object.entries()

`Object.entries()` 메소드는 `for ...in` 과 같은 순서로 `[key, value]` 를 반환합니다

```jsx
const obj = {
	a: 'anything',
	b: 26,
}

Object.entries(obj); // -> ["a", "anything"] ["b", 26]
```