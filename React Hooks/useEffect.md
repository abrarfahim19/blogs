## useEffect

It allows us to perform side effect. That's why it is called useEffect. And that effect takes place after every render.

The blue print-

```js
useEffect(<fuction>, <dependency>);

useEffect(()=> {

},[])
```

Let's have a look at the code bellow-

```js
const UseEffectComp = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    setTimeout(() => {
      setCount(count + 1);
    }, 1000);
  }, []);

  return (
    <div>
      <h1>I've rendered {count} times!</h1>
    </div>
  );
};
```

Now the train of thought---

What will happen to the component?

1. No dependency passed
2. An empty array
3. props or state value

Analyze the code bellow, and what will happen?

```js
function Counter() {
  const [count, setCount] = useState(0);
  const [calculation, setCalculation] = useState(0);

  useEffect(() => {
    setCalculation(() => count * 2);
  }, [count]); // <- add the count variable here

  return (
    <>
      <p>Count: {count}</p>
      <button onClick={() => setCount((c) => c + 1)}>+</button>
      <p>Calculation: {calculation}</p>
    </>
  );
}
```

### Effect CleanUP

some effects require cleanup to reduce memory leaks.

`According to React’s official documentation, “React performs the cleanup when the component unmounts. However… effects run for every render and not just once. This is why React also cleans up effects from the previous render before running the effects next time.”`

Do you understand the following code?

```js
const UseEffectComp = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    let timer = setTimeout(() => {
      setCount((count) => count + 1);
    }, 1000);

    return () => clearTimeout(timer);
  }, []);

  return (
    <div>
      <h1>I've rendered {count} times!</h1>
    </div>
  );
};
```

`Note: To clear the timer, we had to name it.`

_useEffect_ has two types of side effects: those that don’t need cleanup and those that do need cleanup like the examples we’ve seen above + fetch requests. It is very vital we learn when and how to use the cleanup function of the _useEffect_ Hook to prevent memory leaks and optimize applications.
