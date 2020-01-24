---
layout: post
title:      "Function Components vs Class Components "
date:       2020-01-23 19:37:56 -0500
permalink:  function_components_vs_class_components
---


**Function Components**


Functional components are essentially JavaScript (or ES6) functions that  return a React element. Here is an example from the documentation:

```

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>
}
 
```

As you can see in the above example, functional components are basically JavaScript functions. They can accept props as an argument, and use JSX to parse JavaScript expressions. For example {props.name}.

## Class Components

On the other hand, Class Components have more functionality that they inherit from React's Component class. Here's the same example as above using a Class Component:

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

At a glance, it is obvious that a Class Component has more code to it than a Function Component. However, the render method is not optional in the Class Component. And this is just a simple presentational component. But let's have a look at what we gain. 

## State keeping track of things

Props give us the ability to pass down from a parent component to a child component. So, how can we pass back up information from a child to a parent, or simply change a value in the very same component? Here is where state comes to the rescue.

Here is a great demonstration for using state. In an instance where we have a button in a child component and would like to keep track of how many times that button was clicked, it would look something like this:


```
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {count: 0};
    this.handleClick = this.handleClick.bind(this);
  }
  
  handleClick() {
    this.setState(state => ({
      count: state.count + 1
    }));
  }
  
  render() {
    return (
      <div>
        <h2>{this.state.count}</h2>
        <button onClick={handleClick}>
          click
        </button>
      </div>
    )
  }
}
```


First we set up 'count' in the state with a value of ‘0'. Then, to increment the count and update the state In the render method we add a onClick handler which will evoke the value passed in itself (in our case it’s handleClick) which uses setState to update the value of the state we are passing in.

 The amazing thing with react is, that when updating state it will only re-render the component with the state that is getting updated.

