# Chapter 1: Crash Course of React
In this chapter, we will build a tic-tac-toe application in order to learn the React basic by getting our hands dirty to learn from implementing. The exercise assume you have some understanding of Javascript, HTML components, and have never done any exercise in React, and we will go over step-by-step how to set up and build the application. The goal is to follow the instruction from the <a href="https://reactjs.org/">React official site</a> and learn from it.
<br><br>
Only relevant files are available in this folder. If you want to run the application, initialize the React project and replace the files available in this folder with the files in the React project folder.

## How to Set Up an React Application
Once you have installed <a href="https://nodejs.org/en/">Node.js</a>, change your directory to where you want to save the project folder. Let's assume we will save the project folder on desktop and run these command:
<br>

```
# Initialize the project
npx create-react-app my-app

# Delete the scripts in the src folder
cd my-app
cd src
rm -f *
# Change directory back to the project folder 
cd ..
```
<br>
Then, add <b>index.css</b> with this <a href="https://codepen.io/gaearon/pen/oWWQNa?editors=0100">CSS code</a> and <b>index.js</b> in the <b>src</b> folder. In the index.js file, copy and paste the following lines to the top, and paste the script from this <a href="https://codepen.io/gaearon/pen/oWWQNa?editors=0010">link</a>.
<br>

```
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
```

<br>
In this repository, we will only save the script in the src folder.
<br><br>
Once it is done, we can run this on port 7761:
<br>

```
npm start --port 7761
```
<br>
If it does not work, change the parameter in <i>package.json</i>. Under <i>scripts</i>, update the <i>start</i> key from <i>react-scripts start</i> to <i>PORT=7761 react-scripts start</i> like below:

```
scripts:{
  "start": "PORT=7761 react-scripts start",
  ...
}
```

<br><br>
And there should be a browser opened, and redirect to <i>localhost:7761</i>

## Some Basics about React
React is a declarative Javascript library for building user interfaces. React allows you to build complex UI using <i>components</i> like Lego blocks.
<br><br>
Let's start with <i>React.Component</i>, it is a component to tell React what we want to see on the screen. It takes <b>props</b> (Short for properties), and return a hierarchy of views to display via the <i>render()</i> method, which returns a React element. An example looks like this:
<br>
```
class ShoppingList extends React.Component {
  render() {
    return (
      <div className="shopping-list">
        <h1>Shopping List for {this.props.name}</h1>
        <ul>
          <li>Apple</li>
          <li>Orange</li>
          <li>Strawberry</li>
        </ul>
      </div>
    );
  }
}
```

<br>
Alternatively, you may use the following syntax:
<br>

```
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', {}, Shopping List for, props.name),
  React.createElement('ul', 
  	{},
  	React.createElement('li',{},'Apple'),
  	React.createElement('li',{},'Orange'),
  	React.createElement('li',{},'Strawberry')
  )
);
```

## Building the Application
### Create a Basic Game
In the starter coder, there are 3 React components:
<ul>
	<li>Square</li>
	<li>Board</li>
	<li>Game</li>
</ul>
<br>
The Square component renders a single <i>button</i> and the Board renders 9 squares. The Game component renders a board with placeholder values.
<br><br>
In the first approach, we will use a constructor class to initialize the state in Square. Then, in the render() function, we will add a onClick function to set the state after the user has clicked, and return the current state value. Once it is done, we are able to click on the square and display 'X'.
<br><br>
However, each Square component maintains its state and we need to have each squares in one location, ie, Board, we will need to declare a constructor in the Board class with an array of squares, replace the Square render function to the current state, and add a handleClick function on onClick function in Square render function. Then, replace Square as a function rather than class due to syntax simplicity as function only contain a render method and don't have their own state.
<br><br>
We will add an additonal instance in Board to keep track who takes the turn by adding <i>xIsNext</i>, as well as updating the handleClick function to alternative the turns.
<br><br>
To deterine a winner, we will add a function to check the array values and update the Board render function in order to trigger the function to check for winner. 
<br><br>
Now, we have just created a basic tic-tac-toe!

### Finalize with Better Features
Coming soon...