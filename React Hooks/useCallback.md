## useCallback

The React useCallback Hook returns a memoized callback function.

The useCallback and useMemo Hooks are similar. The main difference is that useMemo returns a _memoized value_ and useCallback returns a _memoized function_.

One reason to use useCallback is to prevent a component from re-rendering unless its props have changed.

UseCallback.jsx

```js
import { useState } from "react";
import ReactDOM from "react-dom/client";
import Todos from "./Todos";

const UseCallback = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState([]);

  const increment = () => {
    setCount((c) => c + 1);
  };
  const addTodo = () => {
    setTodos((t) => [...t, "New Todo"]);
  };

  return (
    <>
      <Todos todos={todos} addTodo={addTodo} />
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
      </div>
    </>
  );
};

export default UseCallback;
```

Todo.jsx

```js
import { memo } from "react";

const Todos = ({ todos, addTodo }) => {
  console.log("child render");
  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => {
        return <p key={index}>{todo}</p>;
      })}
      <button onClick={addTodo}>Add Todo</button>
    </>
  );
};

export default memo(Todos);
```

In here the `Todo` component will rerender even when we are clicking on the `count increament`

**To fix this, we can use the useCallback hook to prevent the function from being recreated unless necessary.**

```js
const addTodo = useCallback(() => {
  setTodos((t) => [...t, "New Todo"]);
}, [todos]);
```

This time onClick to count the component will not change it will change only when the todo prop changes.
