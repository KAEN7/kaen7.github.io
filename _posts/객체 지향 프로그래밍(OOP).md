# 객체 지향 프로그래밍(OOP)

`객체 지향 프로그래밍(Object-oriented programming)` 은 절차 지향 프로그래밍과는 다르게 데이터와 기능을 한데 묶어서 처리합니다

속성과 메소드가 하나의 `객체` 라는 개념에 포함되며 이는 자바스크립트 `object` 와는 다르게 `클래스(class)` 라는 이름으로 부릅니다

### class 정의

ES5 클래스는 함수로 정의할 수 있습니다

```jsx
function Cat(brand, name, color) {
  // 인스턴스가 만들어질 때 실행되는 코드
}
```

ES6에서는 class라는 키워드를 이용해서 정의할 수 있습니다

```jsx
class Car {
  constructor(brand, name, color) {
    // 인스턴스가 만들어질 때 실행되는 코드
  }
}
```

여기서 만들어지는 함수는 객체지향 프로그래밍에서 `생성자(constructor) 함수` 라고 불립니다

참고로 `return` 값을 만들지 않습니다
