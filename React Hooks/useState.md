## useState

It lets you initialize a state and then update the state with a function.

### Basic blueprint

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

So the concept that needs to cleared is following:

1. import useState
2. Initialize State
3. Read State
4. Update State
5. What the state can hold (can it hold object?)
6. Updating object and Arrays in state.
