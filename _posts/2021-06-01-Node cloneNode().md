# Node.cloneNode()

`Node.cloneNode()` 메소드는 이 메소드를 호출한 Node의 복제된 Node를 반환합니다

```jsx
let dupNode = node.clondNode(deep);
```

- node

    복제되어야할 node

- dupNode
복제된 새로운 node
- deep `Optional`

    해당 node의 children까지 복제하려면 `true`, 해당 node만 복제하려면 `false`