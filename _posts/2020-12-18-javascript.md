---
title: 바닐라 자바스크립트
categories: [JavaScript]
comments: true
---

# 바닐라 자바스크립트
잘 모르는 것 위주로 작성중

## 정의
웹페이지에 생동감을 불어넣기 위해 만들어진 프로그래밍 언어

자바스크립트로 작성한 프로그램을 스크립트(script)라고 부름

## 자바스크립트 기본

### 코드 구조

#### 변수
데이터를 저장할 때 쓰이는 '이름이 붙은 저장소'  
자바스크립트에선 `let` 키워드를 사용해 변수를 생성  

아래 문(statement)은 'sample'이란 이름을 가진 변수명을 생성(선언)  
``` javascript
let sample = 'Test!'; // 값으로 문자열을 할당

console.log(sample) // Test!
```

다양한 방식으로 정의가능
``` javascript
let user = 'Kaen',
    age = 25,
    message = 'kusdsuna@naver.com';
```

변수는 두 번 선언하면 에러가 발생함

``` javascript
let message = 'Error?';

// 'let'을 반복하면 에러가 발생함
let message = 'errrrrrrrrror'; // SyntaxError: 'message' has already been declared
```

#### 변수 명명 규칙
자바스크립트에선 변수 명명시 두 가지 제약 사항이 있음
1. 변수명에는 오직 문자와 숫자, 그리고 기호 `$`와 `_`만 들어갈 수 있음
2. 첫 글자는 숫자가 될 수 없음
3. 카멜 표기법(camelCase)를 사용!

예약어 목록에 있는 단어는 변수명으로 사용할 수 없음

#### 상수
변화하지 않는 변수를 선언할 땐, `let`대신 `const`를 사용
``` javascript
const myBrithday = '26.02.1996';
```

상수는 재할당 할수 없으므로 상수를 변경하려하면 에러가 발생
``` javascript
const myBrithday = '26.02.1996';

myBrithday = '18.12.2020'; // error, can't reassign the constant!
```

#### 대문자 상수
기억하기 힘든 값을 변수에 할당해 별칭으로 사용하는 오래된 관습
이런 상수는 대문자와 밑줄로 구성된 이름으로 명명함

``` javascript
const COLOR_RED = '#F00';
const COLOR_GREEN = '#0F0';
const COLOR_BLUE = '#00F';
const COLOR_ORANGE = '#FF7F00';

// 이렇게 색상을 정해놓고 사용하고 싶을때 별칭으로 사용가능
let color = COLOR_RED;
console.log(color); // #F00
```

#### 바람직한 변수명
변수명은 간결하고, 명확해야 함. 변수가 담고 있는 것이 무엇인지 잘 설명될수 있어야함.  

아래는 변수 명명시 참고하기 좋은 규칙임
- `userName`이나 `shoppingCart`처럼 사람이 읽을 수 있는 이름을 사용
- 무엇을 하고 있는지 명확히 알고 있지 않을 경우 외에는 줄임말이나 `a`, `b`, `c`같은 짧은 이름은 피함
- 최대한 서술적이고 간결하게 명명

### 자료형
자바스크립트에서 값은 항상 문자열이나 숫자형 같은 특정한 자료형에 속함

``` javascript
// no error
let message = 'hello';
message = 12345;
```
이처럼 자료의 타입은 있지만 변수에 저장되는 값의 타입은 언제든지 바꿀 수 있는 언어를 '동적 타입'언어라고 함

#### 숫자형
``` javascript
let n = 123;
n = 12.345;
```

숫자형은 정수 및 부동소수점 숫자를 나타냄

#### 문자형
자바스크립트에선 문자열(string)을 따옴표로 묶음
``` javascript
let str = "Hello!";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

따옴표에는 세 종류가 있음
1. 큰따옴표: `"Hello"`
2. 작은따옴표: `'Helllo'`
3. 역 따옴표(백틱): ``Hello``

백틱으로 변수나 표현식을 감싼 후 `${...}`안에 넣어주면, 원하는 변수나 표현식을 문자열 중간에 쉽게 얻을 수 있음

#### 불린형
불린형(논리 타입)은 `true`와 `false` 두가지 값밖에 없는 자료형임
`true`는 긍정, `false`는 부정을 의미함

#### null 값
`null` 값은 오로지 `null` 값만 포함하는 별도의 자료형

``` javascript
let age = null;
```

자바스크립트에선 null을 '존재하지 않는 값', '비어있는 값', '알수 없는 값'으로 사용

#### undefined 값
`undefined`는 `null` 값처럼 자신만의 자료형을 형성함
`undefined`는 '값이 할당되지 않은 상태'를 나타낼 떄 사용

#### 객체
`객체(object)` 형은 특수한 자료형임
객체형을 제외한 다른 자료형은 문자열이든 숫자든 한 가지만 표현할 수 있기에 원시 자료형이라 불림

#### 심볼
`심볼(symbol)`형은 객체의 고유한 식별자를 만들때 사용됨

#### typeof 연산자
`typeof` 연산자는 인수의 자료형을 반환함  
자료형에 따라 처리 방식을 다르게 하고 싶거나 변수의 자료형을 빠르게 알아내고자 할때 유용

`typeof` 연산자는 두 가지 형태의 문법을 지원함
1. 연산자: `typeof x`
2. 함수: `typeof(x)`

예시
``` javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

### 형 변환
함수와 연산자에 전달되는 값은 대부분 적절한 자료형으로 자동 변환됨. 이런 과정을 '형 변환'이라고 함

#### 문자형으로 변환
문자형의 값이 필요할 때 일어남

`alert`메소드는 배개변수로 문자형을 받기 때문에 `alert(value)`에서 value 문자형이어야 합니다. 
만약 다른 형의 값을 전달받으면 이 값은 문자형으로 자동 변환됨

`String(value)` 함수를 호출해 전달받은 값을 문자열로 변환할 수 있음
``` javascript
let value = true;
console.log(typeof value); // boolean

value = String(value); // 변수 value엔 문자열 'true'가 저장됨
console.log(typeof value); // string
```

#### 숫자형으로 변환
수학과 관련된 함수와 표현식에서 자동으로 일어남

숫자형이 아닌 값에 `/`를 적용한 경우를 예시로 보임
``` javascript
console.log('6' / '2'); // 3, 문자열이 숫자형으로 자동변환된 후 연산이 수행됨
```

`Number(value)`함수를 호출해 주어진 값을 숫자형으로 명시해서 변환할 수 있음
``` javascript
let str = '123';
console.log(typeof str); // string

let num = Number(str); // 문자열 '123'이 숫자 123으로 변환됨

console.log(typeof num) // number
```

#### 불린형으로 변환
`Boolean(value)`를 호출하면 명시적으로 불린으로의 형 변환을 수행할 수 있음

변환시 적용되는 규칙
- 숫자 `0`, 빈 문자열, `null`, `undefined`, `Nan`과 같이 직관적으로 '비어있다고' 느껴지는 값들은 `false`가 됨
- 그 외의 값은 `true`로 변환됨

### 기본 연산자와 수학
자바스크립트에서만 제공하는 연산자에 대해 배워보겠음

#### 용어: '단항', '이항', '피연산자'
- `피연산자`는 연산자가 연산을 수행하는 대상.
    예를 들어 `5 * 2`에는 왼쪽 피연산자 `5`와 오른쪽 피연산자 `2`, 총 두 개의 피연산자가 있음
- 피연산자를 하나만 받는 연산자는 `단항 연산자`라고 부름.
    피연산자의 부호를 뒤집는 단항 마이너스 연산자 `-`는 단항 연산자의 대표적인 예

    ``` javascript
    let x = 1;

    x = -x;
    console.log(x); // -1, 단항 마이너스 연산자는 부호를 뒤집음
    ```







[출처](https://ko.javascript.info/intro)