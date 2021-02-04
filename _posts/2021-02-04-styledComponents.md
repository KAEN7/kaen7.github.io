---
title: styled-components
categories: [REACT]
comments: true
---

# styled-components란?
javascript파일 내에서 CSS를 사용할 수 있게 해주는 대표적인 CSS-in-JS 라이브러리로써 스타일링을 위한 프레임워크  
자유로운 CSS 커스텀 컨포넌트를 만들 수 있음

- 설치
    ```
    $ npm install --save styled-components
    ```

- 구조
    ``` jsx
    const {component명} = style.{태그명}`
        스타일
    `;
    ```

- 예시
    ``` jsx
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

출처: [velog](https://velog.io/@djaxornwkd12/Styled-Component%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)