### React Query 개요

리액트 데이터 페칭을 위한 라이브러리로써 **데이터를 페칭**하고 **동기화**시키면서 **캐싱**처리도 해주는 라이브러리입니다

### 사용하는 이유

리액트에서는 Hook을 사용해 데이터를 페칭하거나 상태 관리 라이브러리를 통해 데이터를 저장하고 관리했습니다

이러한 데이터 관리방법은 프론트 상태를 관리하기에는 알맞지만 **서버 상태**를 다루기에는 알맞지 않습니다

서버 상태는 다음과 같습니다

-  컨트롤할 수 없는 위치에 원격으로 유지됨
-  가져오고 업데이트하기 위한 비동기 API가 필요함
-  공유된 소유권을 암시하여 사용자 모르게 다른 사람이 변경할 수 있음
-  주의하지 않으면 최신 상태를 유지하지 못할 수 있음

애플리케이션에서 서버 상태의 특성을 파악해보면 **다음과 같은 문제**들이 있습니다

-  캐싱
-  동일한 데이터에 대한 여러번의 요청을 단일 요청으로 중복 제거
-  오래된 데이터를 업데이트 하는 것
-  언제 데이터가 유효하지 않은지 아는 것
-  최대한 빠르게 데이터 업데이트를 반영하는 것
-  페이지네이션과 Lazy Loading 같은 성능 최적화
-  서버 상태에 대한 메모리 관리와 가비지 컬렉션

React Query는 이러한 까다로운 서버 상태 관리를 해결하기에 적합한 라이브러리입니다

### 장점

React Query는 다음과 같은 기술적인 장점이 있습니다

- 복잡하고 이해하기 어려운 어려줄의 코드를 몇줄로 요약해서 서버 상태를 컨트롤 할 수 있습니다
- 환경 설정에 대한 걱정 없이 애플리케이션을 유지보수하기 쉬워지고 새로운 기능을 구축하기 쉬워집니다
- 애플리케이션을 빠르고 좋은 성능으로 만들어서 사용자에게 좋은 경험을 제공할 수 있습니다
- 잠재적으로 대역폭을 절약하고 메모리 성능을 높이는데 도움이 됩니다

### 코드 예시

```
import { QueryClient, QueryClientProvider, useQuery } from "react-query";

const queryClient = new QueryClient();

export default function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Example />
    </QueryClientProvider>
  );
}

function Example() {
  const { isLoading, error, data } = useQuery("repoData", () =>
    fetch("https://api.github.com/repos/tannerlinsley/react-query").then(
      (res) => res.json()
    )
  );

  if (isLoading) return "Loading...";

  if (error) return "An error has occurred: " + error.message;

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.description}</p>
      <strong>{data.subscribers_count}</strong>{" "}
      <strong>{data.stargazers_count}</strong>{" "}
      <strong>{data.forks_count}</strong>
    </div>
  );
}
```
