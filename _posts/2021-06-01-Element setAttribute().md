# Element.setAttribute()

지정된 요소의 속성 값을 설정합니다

속성의 현재값을 얻으려면 `getAttribute()` 를 사용

속성을 제거하려면 `removeAttribute()` 를 사용합니다

```jsx
Element.setAttribute(key, value);

// key = 속성의 이름
// value = 속성에 할당할 값

ex)
document.setAttribute('id', 'tester');
id가 tester인 DOM을 가져옴
```