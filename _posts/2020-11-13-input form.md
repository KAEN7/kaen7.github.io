---
title : "input form"
category :
    - HTML
tag :
    - HTML, input, form
toc : true
---

# label
사용자 인터페이스 항목의 설명을 나타냄
`<input>`과 연관 시키려면 input 태그에 `id`속성을 넣고 `<label>`의 `for`속성에 같은 값을 넣어주면 됨

- `<label>` 사용시 이점
    - 프로그래밍적으로 텍스트와 input의 관계를 더 쉽게 알게됨
    - 관련 `label`을 클릭하는 것으로 `input` 자체를 활성화 시킬 수 있음

# input
웹 기반 양식에서 사용자의 데이터를 주고 받을 수 있는 대화형 컨트롤을 생성
HTML에서 제일 강력하고 복잡한 요소

```
<form>
    <input type='text'>
</form>
```

- `type` 특성
특성을 지정하지 않은 경우 기본값은 `text`임
[type 유형](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input)

- `input`에는 아주 다양한 특성이 있음
[특성](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input)

# form
사용자가 입력하거나 선택한 정보를 서버로 전송하기 위해 사용

백엔드 서버에 양식을 전달해서 정보를 처리할 수 있게 하는 역할

```
<form 속성 = '속성 값'></form>
```

- 속성
    - action
    폼 데이터가 전송할 서버의 스크립트 파일을 지정

    ```
    <form action='전송위치'></form>
    ```

    - method
        폼을 전송할 방식을 선택
        - get
        url로 넘어가는 방식으로 클라이언트가 폼 데이터를 이름과 값이 결합된 형태로 전달
        전송 가능한 데이터의 크기에 한계가 있으며, 전송 내용이 그대로 노출됨

        - post
        클라이언트와 서버간의 약속된 형식으로 인코딩하여 서버로 전송하는 방식
        데이터를 body로 연결하여 전송하는 방식
        웹 브라우저에서 접근이 불가능해서 get 방식보다 보안에 강함
        전송할 수 있는 데이터의 길이에 제한이 없음

    ```
    <form method='post'></form>
    ```

    - target
        데이터를 제출한 후 받은 응답을 표시할 위치를 나타내는 속성

        - 키워드
            - _self
            현재 브라우저에 표시
            - _blank
            새로운 브라우저에 표시(새탭)
            - _parent
            현재 브라우저 부모에 표시, 존재하지 않으면 현재 브라우저에 표시
            - _top
            최상단 브라우저에 표시

    ```
    <form target='_self'></form>
    ```

[출처](https://blog.naver.com/jaeeun_98/222071568997 '새싹개발자')