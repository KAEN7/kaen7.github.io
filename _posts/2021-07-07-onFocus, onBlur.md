# onFocus, onBlur

`onFocus` 포커스를 받은 경우 이벤트 설정

`onBlur` 포커스가 해지될 때 이벤트 설정

```jsx
const handleBlur = () => {
    console.log('포커스 빠짐!!!!!');
};

onBlur={() => handleBlur}
```