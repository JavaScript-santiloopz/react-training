# Events


### Prevent default event in React
You cannot return false to prevent default behavior in React. You must call preventDefault explicitly.


### Binding `this` in React
If calling bind annoys you, there are two ways you can get around this. If you are using the experimental public class fields syntax, you can use class fields to correctly bind callbacks:
```javascript
class LoggingButton extends React.Component {
  // This syntax ensures `this` is bound within handleClick.  // Warning: this is *experimental* syntax.  handleClick = () => {    console.log('this is:', this);  }
  render() {
    return (
      <button onClick={this.handleClick}>
        Click me
      </button>
    );
  }
}

```
or
```javascript
class LoggingButton extends React.Component {
  handleClick() {
    console.log('this is:', this);
  }

  render() {
    // This syntax ensures `this` is bound within handleClick
    return (button onClick={() => this.handleClick()}>Click me</button>);
  }
}

```
The problem with this syntax is that a different callback is created each time the LoggingButton renders. In most cases, this is fine. However, if this callback is passed as a prop to lower components, those components might do an extra re-rendering. We generally recommend binding in the constructor or using the class fields syntax, to avoid this sort of performance problem.