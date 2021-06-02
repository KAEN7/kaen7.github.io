# Number.prototype.toFixed()

`Number.prototype.toFixed()` 메소드는 숫자를 고정 소수점 표기법으로 표기해 반환합니다

```jsx
function financial(x) {
  return Number.parseFloat(x).toFixed(2);
}

console.log(financial(123.456));
// expected output: "123.46"

console.log(financial(0.004));
// expected output: "0.00"

console.log(financial('1.23e+5'));
// expected output: "123000.00"
```