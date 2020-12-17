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
















[출처](https://ko.javascript.info/intro)