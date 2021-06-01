# Element.remove()

`Element.remove()` 메소드는 해당 요소가 속한 트리에서 요소를 제거합니다

```jsx
remove()

// ex)
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<div id="div-03">Here is div-03</div>

var el = document.getElementById('div-02');
el.remove(); // Removes the div with the 'div-02' id
```