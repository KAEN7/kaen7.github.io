# Object.keys()

`Object.keys()` 함수는 파라미터로 입력받은 객체의 key 목록을 배열로 리턴합니다

```jsx
const obj = {
	name: 'sunghun',
	nickname: 'kaen',
	age: 26
};

let arr = Object.keys(obj) // (3) ["name", "nickname", "age"]
arr.length; // 3
```