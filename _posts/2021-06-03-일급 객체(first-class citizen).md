# 일급 객체(first-class citizen)

특별한 대우를 받는 함수입니다

아래와 같이 특별하게 취급됩니다

- 변수에 할당할 수 있다

    ```jsx
    // 함수는 일급 객체이기에 변수에 저장할 수 있습니다
    const sample = function(x) {
    	return x++;
    }

    // sample에 함수가 저장되어 있으므로 ()를 사용해 함수를 호출할 수 있습니다
    result = sample(1);
    console.log(result); // 2
    ```

- 다른 함수의 인자로 전달될 수 있다
- 다른 함수의 결과로서 리턴될 수 있다