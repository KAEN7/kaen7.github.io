# Spread / Rest

## Spread

주로 배열을 풀어서 인자로 전달하거나, 배열을 풀어서 각각의 요소에 넣을 때에 사용합니다

기존 배열을 변경하지않고 복사하듯이 사용됩니다

```jsx
function sum(a, b, c) {
	return a + b + c;
}

const num = [1,2,3];

sum(...num); // 6
```

배열 합치기

```jsx
let arr1 = [3, 4, 2];
let arr2 = [1, 8, 5];
arr1 = [...arr1, ...arr2]; // (6) [3, 4, 2, 1, 8, 5]
```

배열 복사

```jsx
let arr1 = [4, 8, 1];
let arr2 = [...arr1];
arr2.push(1);

console.log(arr1, arr2);
// (3) [4, 8, 1] (4) [4, 8, 1, 1]
```

객체에서 사용하기

```jsx
let obj1 = { name: 'tree', real: true };
let obj2 = { name: 'none', real: false };

let clone = { ...obj1 };
let merge = { ...obj1, ...obj2 };

console.log(clone, merge);
// {name: "tree", real: true} 
// {name: "none", real: false}
```

## Rest

파라미터를 배열의 형태로 받아서 사용할 수 있습니다

파라미터 개수가 가변적일 때 유용합니다

```jsx
function sum(...theArgs) {
  return theArgs.reduce((previous, current) => {
    return previous + current;
  });
}

console.log(sum(1, 2, 3));
// expected output: 6

console.log(sum(1, 2, 3, 4));
// expected output: 105
```

함수에서 나머지 파라미터 받아오기

```jsx
function num(a, b, ...parameter) {
	console.log('a', a);
	console.log('b', b);
	console.log('parameter', parameter);
}

num('mon', 'thu', 'wed');

// a mon 
// b thu 
// parameter (1) ["wed"]
```