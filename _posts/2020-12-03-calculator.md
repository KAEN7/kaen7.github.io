---
title : "calculator"
category :
    - JavaScript
tag :
    - JavaScript
toc : true
---
# 계산기 코드

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="reset.css">
  <link rel="stylesheet" href="style.css">
  <title>calculator</title>
</head>
<body>
  <h1>CALCULATOR</h1>
  <header>
    <input type="text" id="hideCal"/>
    <input type="text" id="calculator" />
    <button id="clearBtn">C</button>
  </header>
  <main>
    <div id="numbers">
      <div class="groupOne">
        <button value="1" id="one">1</button>
        <button value="2" id="two">2</button>
        <button value="3" id="three">3</button>
      </div>
      <div class="groupTwo">
        <button value="4" id="four">4</button>
        <button value="5" id="five">5</button>
        <button value="6" id="six">6</button>
      </div>
      <div class="groupThree">
        <button value="7" id="seven">7</button>
        <button value="8" id="eight">8</button>
        <button value="9" id="nine">9</button>
      </div>
      <div class="groupFour">
        <button value="" id="zero">0</button>
        <button id="equals">=</button>
      </div>
    </div>
    <div id="symbol">
      <button value="+" id="plus">+</button>
      <button value="-" id="minus">-</button>
      <button value="*" id="multiple">*</button>
      <button value="/" id="division">/</button>
    </div>
  </main>

  <script src="app.js"></script>
</body>
</html>
```

```css
body {
    background: black;
    display: flex;
    flex-direction: column;
    color: white;
    margin-top: 150px;
    align-items: center;
}

h1 {
    font-size: 60px;
    font-weight: 900;
    margin-bottom: 15px;
    border-bottom: 1px solid darkgray;
}

button {
    display: flex;
    border-radius: 12px;
    width: 100px;
    height: 50px;
    margin: 3px;
    justify-content: center;
    align-items: center;
    color: white;
    font-weight: 800px;
    font-size: 17px;
    border: 1px solid black;
    outline: none;
}

button:active {
    transform: scale(1.06);
    
}

header {
    display: flex;
    margin-left: 6px;
}

#calculator {
    display: flex;
    flex-basis: 3;
    width: 307px;
    height: 50px;
    background: black;
    box-shadow: none;
    color: white;
    outline: none;
    border: none;
}

#hideCal {
    display: none;
}

#clearBtn {
    display: flex;
    flex-basis: 1;
    background: rgb(179, 179, 179);
    margin-left: 6px;
}

main {
    display: flex;
}

#numbers .groupOne,
    .groupTwo,
    .groupThree,
    .groupFour {
    display: flex;
    flex-direction: row;
}

#numbers button {
    background: rgb(55, 54, 54);
}

#zero {
    width: 206px;
}

#symbol button {
    background: orange;
    margin-bottom: 6px;
}
```

```javascript
// CONST
const cal = document.querySelector('#calculator');
const hideCal = document.querySelector('#hideCal');

const clr = document.querySelector('#clearBtn');
const one = document.querySelector('#one'),
    two = document.querySelector('#two'),
    three = document.querySelector('#three'),
    four = document.querySelector('#four'),
    five = document.querySelector('#five'),
    six = document.querySelector('#six'),
    seven = document.querySelector('#seven'),
    eight = document.querySelector('#eight'),
    nine = document.querySelector('#nine'),
    zero = document.querySelector('#zero');
const eqlOn = document.querySelector('#equals');
const plus = document.querySelector('#plus');
const minus = document.querySelector('#multiple');
const division = document.querySelector('#division');

// function
function calculator() {
    const hideCal = document.querySelector('#hideCal');
    const result = eval(hideCal.value);
    const cal = document.querySelector('#calculator');
    cal.value = result;
}

function outPut(num) {
    const hideCal = document.querySelector('#hideCal');
    hideCal.value = hideCal.value + num.target.value;
}

function clearCal() {
    const hideCal = document.querySelector('#hideCal');
    hideCal.value = '';
    const cal = document.querySelector('#calculator');
    cal.value = '';
}

// if
if(clr) {
    clr.addEventListener('click', clearCal);
}

if(one) {
    one.addEventListener('click', outPut);
}
if(two) {
    two.addEventListener('click', outPut);
}
if(three) {
    three.addEventListener('click', outPut);
}
if(four) {
    four.addEventListener('click', outPut);
}
if(five) {
    five.addEventListener('click', outPut);
}
if(six) {
    six.addEventListener('click', outPut);
}
if(seven) {
    seven.addEventListener('click', outPut);
}
if(eight) {
    eight.addEventListener('click', outPut);
}
if(nine) {
    nine.addEventListener('click', outPut);
}
if(zero) {
    zero.addEventListener('click', outPut);
}

if(plus) {
    plus.addEventListener('click', outPut);
}
if(minus) {
    minus.addEventListener('click', outPut);
}
if(multiple) {
    multiple.addEventListener('click', outPut);
}
if(division) {
    division.addEventListener('click', outPut);
}
if(eqlOn) {
    eqlOn.addEventListener('click', calculator);
}
```

if문 코드가 많이 지저분함;;