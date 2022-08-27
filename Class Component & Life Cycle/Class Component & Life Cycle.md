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
