## Class Component

In react we use class component like this.

```js
class Clock extends React.Componet {
  state = { date: new Date() };

  componentDidMount() {
    this.clockTimer = setInterval(() => this.tick(), 1000);
  }

  componentWillUnmount() {
    clearInterval(this.clockTimer);
  }

  tick() {
    this.setState({
      date: new Date(),
    });
  }

  reder() {
    return <h2>{this.state.date}</h2>;
  }
}
```

another performance imprvement can be done with _shouldComponentUpdate()_

```js
shouldComponentUpdate(nextProps,nextState){
  if (this.props.color !== nextProps.color) {
    return true;
  }
  if (this.state.count !== nextState.count) {
    return true;
  }
  return false;
}
```
