## useRef

The hook allows to persis values between renders.

- It can be used to store mutable value that does not cause re-render when updated.
- It can be used to access DOM element directly.

### Does not cause Re-Render

```js
function UseRefComp() {
  const [inputValue, setInputValue] = useState("");
  const count = useRef(0);

  useEffect(() => {
    count.current = count.current + 1;
  });

  return (
    <>
      <input
        type="text"
        value={inputValue}
        onChange={(e) => setInputValue(e.target.value)}
      />
      <h1>Render Count: {count.current}</h1>
    </>
  );
}
```

useRef is like an object so `const count = useRef(0)` means `const count = {current: 0}`

### Accessing DOM Element

```js
function UseRefComp() {
  const inputElement = useRef();

  const focusInput = () => {
    inputElement.current.focus();
  };

  return (
    <>
      <input type="text" ref={inputElement} />
      <button onClick={focusInput}>Focus Input</button>
    </>
  );
}
```

### Tracking State Changes

```js
function UseRefEffect() {
  const [inputValue, setInputValue] = useState("");
  const previousInputValue = useRef("");

  useEffect(() => {
    previousInputValue.current = inputValue;
  }, [inputValue]);

  return (
    <>
      <input
        type="text"
        value={inputValue}
        onChange={(e) => setInputValue(e.target.value)}
      />
      <h2>Current Value: {inputValue}</h2>
      <h2>Previous Value: {previousInputValue.current}</h2>
    </>
  );
}
```

This time we use a combination of _useState_, _useEffect_, and _useRef_ to keep track of the previous state.
