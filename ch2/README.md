# Chapter 2: Basic Syntax and Components
In this chapter, we will go over the materials in <a href="https://www.w3schools.com/react/react_class.asp">w3 Schools React Class Components</a>.

## Class and Render
You may declare a class and define <i>render()</i> to render. Then you may declare a root to render this class.
<br>
```
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

## Reference
<a href="https://www.w3schools.com/react/react_class.asp">w3 Schools React Class Components</a>