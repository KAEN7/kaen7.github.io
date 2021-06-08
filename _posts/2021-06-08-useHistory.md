# useHistory

useHistory는 기존에 **history.push('/')**로 많이 사용하던 history와 같은 기능을 한다

페이지 이동에 사용할 수 있는 history 인스턴스에 접근한다

```jsx
import { useHistory } from "react-router-dom";

function HomeButton() {
  let history = useHistory();

  function handleClick() {
    history.push("/home");
  }

  return (
    <button type="button" onClick={handleClick}>
      Go home
    </button>
  );
}
```

### history

1. 브라우저의 *window.history* 와 유사
2. 주소를 임의로 변경하거나 되돌아 갈 수 있도록 한다.
3. 주소 변경시, SPA 특성을 지키기 위해 페이지 전체를 리로드 하지 않는다.
4. location 이 포함되어 있다.