## useState

basic blueprint

```js
const [count, setCount] = useState(0);

const handleIncrease = () => {
  setCount(count + 1);
};

const handleDecrease = () => {
  setCount(count - 1);
};
const handleReset = () => {
  setCount(0);
};
```

we can also use Object as default state and change one perticular key-value with `...` operator of js.
