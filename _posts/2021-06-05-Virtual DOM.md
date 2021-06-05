# Virtual DOM

Virtual DOM은 html 객체에 기반한 자바스크립트 객체로 표현할 수 있습니다

공식문서에서는 `UI의 가상적인 표현을 메모리에 저장하고 ReactDOM과 같은 라이브러리에 의해 실제 DOM과 동기화` 라고 설명하고있습니다 ⇒ 재조정

![Virtual%20DOM%20bc77968a98374d7da5f9f6b2e41871aa/Untitled.png](Virtual%20DOM%20bc77968a98374d7da5f9f6b2e41871aa/Untitled.png)

그리고 이러한 처리는 실제 DOM이 아닌 메모리 상에서 동작하기 때문에 훨씬 더 빠르게 동작합니다

그리고 실제 렌더링이 아니기에 연산 비용이 최소화됩니다

## Virtual DOM의 동작 원리

실제 DOM Object와 같은 속성들을 가지고 있지만 실제 DOM이 갖고 있는 api는 갖고 있지 않습니다

바뀐 부분만 실제 적용 시킵니다, 즉 전체 real DOM을 바꾸지 않고도 필요한 UI의 업데이트를 적용할 수 있습니다
