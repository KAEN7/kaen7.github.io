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

### new 키워드

`new` 키워드를 사용해 클래스의 인스턴트를 만들어낼 수 있습니다

```jsx
let avante = new Car("hyundai", "avante", "black");
let mini = new Car("bmw", "mini", "white");
let beetles = new Car("volkswagen", "beetles", "red");
```

각각의 인스턴스는 Car라는 클래스의 고유한 속성과 메소드를 갖습니다

속성과 메소드

속성 먼저 보겠습니다

```jsx
// ES5
function Cat(brand, name, color) {
  this.brand = brand;
  this.name = name;
  this.color = color;
}
```

```jsx
// ES6
class Car {
  constructor(brand, name, color) {
    this.brand = brand;
    this.name = name;
    this.color = color;
  }
}
```

여기서 `this` 는 인스턴스 객체를 의미합니다

그 다음은 메소드입니다

```jsx
// ES5
function Car(brand, name, color) { ... }

Car.prototype.refuel = function () {
	// 연료 공급을 구현하는 코드
}

Car.prototype.drive = function () {
	// 운전을 구현하는 코드
}

// ES6
class Car {
	constructor(brand, name, color) { ... }

	refuel() {
		// 연료 공급을 구현하는 코드
	}

	drive() {
		// 운전을 구현하는 코드
	}
}
```

## 인스턴스에서의 사용

```jsx
let avante = new Car('hyundai', 'avante', 'black');
avante.color; // 'black'
avante.drive()' // 아반떼가 운전을 시작합니다

let mini = new Car('bmw', 'mini', 'white');
mini.brand; // 'bmw'
mini.refule(); // 미니에 연료를 공급합니다
```

## 클래스와 인스턴스

`클래스` 는 일종의 원형(original form)으로 객체를 생성하기 위한 아이디어나 청사진입니다

`인스턴스` 는 클래스의 사례(instance object) 입니다

클래스는 객체를 만들기 위한 `생성자(constructor)` 함수를 포함합니다

## OOP의 4가지 기본컨셉

### 캡슐화

- 데이터와 기능을 하나의 단위로 묶는 것
- 은닉
  구현은 숨기고, 동작은 노출시킴
- 느슨한 결합에 유리
  언제든 구현을 수정할 수 있음
  느슨할 결합은 코드 실행 순서에 따라 절차적으로 코드작성하는 것이 아닌 `실제 모습과 닮게 코드를 모아 결합하는 것`을 의미

즉 코드가 복잡해지지 않게 만들고 재사용성을 높입니다

### 추상화

`추상화` 란 내부 구현은 아주 복잡한데 실제로 노출되는 부분은 단순하게 만든다는 개념입니다

클래스 정의 시 메소드와 속성만 정의한 것을 `인터페이스` 라고 부릅니다 이것이 추상화의 본질입니다

즉 코드가 복잡하지 않게 만들며 단순화된 사용으로 변화에 대한 영향을 최소화합니다

### 상속

`상속` 이란 부모 클래스의 특징을 자식 클래스가 물려받는 것입니다

자세하게는 `기본 클래스(base class)` 의 특징을 `파생 클래스(derive class)` 가 상속받는다가 정확합니다

즉 불필요한 코드를 줄여서 재사용성을 높입니다

### 다형성

`다형성(Polymorphism)` 이란 다양한 형태라는 말입니다

즉 객체가 똑같은 메소드라 하더라도 다른 방식으로 구현될 수 있음을 뜻합니다

위 그림은 `render()` 라는 이름이 같은 메소드들이 다른 Element에 들어가서 다르게 동작되는 것을 보여줍니다

즉 다형성으로 인해 동일한 메소드에 대해 조건문 대신 객체의 특성에 맞게 작성할 수 있게됩니다

## 클래스와 프로토타입

Javascript는 `프로토타입(원형 객체) 기반 언어` 입니다
