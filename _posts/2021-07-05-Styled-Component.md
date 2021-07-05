# Styled-Component

javascript파일 내에서 CSS를 사용할 수 있게 해주는 대표적인 CSS-in-JS 라이브러리로써 스타일링을 위한 프레임워크

자유로운 CSS 커스텀 컨포넌트를 만들 수 있음

- 설치

    ```jsx
    npm install --save styled-components

    // 공식문서에서는 package.json에 다음 코드를 추가하도록 권장합니다
    // 여러 버전의 Styled Component가 설치되어 발생하는 문제를 줄여준답니다
    {
      "resolutions": {
        "styled-components": "^5"
      }
    }
    ```

- 구조

    ```jsx
    const {component명} = style.{태그명}`
          스타일
      `
    ```

- 예시

    ```jsx
    // styled-components 라이브러리에서 import 해온 styled라는 객체를 이용합니다
      // 아래와 같이 h1 태그를 만들어 Title이라는 스타일드 컴포넌트를 만들 수 있습니다

      import styled from 'styled-componets'

      render (
          <Wrapper>
              <Title>
                Hello World!
              </Title>
          </Wrapper>
      );

      const Title = styled.h1`
          font-size: 1.5em;
          text-align: center;
          color: palevioletred;
      `;

      const Wrapper = styled.section`
          padding: 4em;
          background: papayawhip;
      `;
    ```

    ### 함수 전달하기

    예시로 <Button> 컴포넌트의 background 와 color 속성은 primary 라는 props 의 전달 여부에 따라 컬러값을 정의하고 있습니다.

    ```jsx
    // Button component
    ...
      background: ${(props) => (props.primary ? "red" : "white")};
      color: ${(props) => (props.primary ? "white" : "red")};
    ...

    // App component
    ...
      <Button>Normal</Button>
      <Button primary>Primary</Button>
    ...
    ```

    ### 기존 속성 확장

    ```jsx
    // 기존의 Button 컴포넌트에 Blue 컴포넌트만을 위한 새로운 속성 추가
    const Blue = styled(Button)`
      color: blue;
      border-color: blue;
    `;
    ```

    ### Passed props

    ```jsx
    const Input = styled.input`
      padding: 0.5em;
      margin: 0.5em;
      color: ${(props) => props.inputColor || "palevioletred"}; 	// 이거 보세요
      background: papayawhip;
      border: none;
      border-radius: 3px;
    `;

    // ...App
    <Input defaultValue="@probablyup" type="text" />
    <Input defaultValue="@ge" type="text" inputColor="rebeccapurple" /> // 얘도 보세요
    ```

    두번째 Input태그를 보면 inputColor라는 prop로 전달됨에 따라 색상이 바뀌게됩니다

    ## 참조

    [[JavaScript] React - Styled Components 공식문서 basic 따라하기](https://velog.io/@sji7532/JavaScript-React-Styled-Components-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-basic-%EB%94%B0%EB%9D%BC%ED%95%98%EA%B8%B0)