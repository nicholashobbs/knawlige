# selenium
# chrome devtools
# chrome extensions
# puppeteer
# php# owasp top 10
# security tools
# express
# node

`npm -v` to check version



https://nodejs.org/en/download/

# react

## JSX
syntax extension to JavaScript that allows developers to write React components using XML-like syntax. JSX is compiled to JavaScript using Babel

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

function App() {
  return (
    <div>
      <h1>Welcome to React!</h1>
      <p>JSX can evaluate {5*6} any valid js expression in curly braces</p>
    </div>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

## Components
building blocks of React applications, which are used to split the UI into independent, reusable pieces. Components can be defined as classes or functions

```javascript
// renders a button with a function component
function Button() {
  return <button>Click me!</button>;
}

// class component version
class Button extends React.Component {
  render() {
    return <button>Click me!</button>;
  }
}
```


## Props
props are passed to components, allowing them to access data and functionality from the parent component

```javascript
import React from 'react';

// Component using props
function Greeting(props) {
  // uses props passed in
  return <h1>Hello, {props.name}!</h1>;
}

// renders Greeting component with name prop
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Greeting name="John" />);
```

## Hooks
are a way to use React features without writing a class component

## State
used to track and manage data within a component
state is mutable and can be changed over the lifetime of a component, as opposed to props which are immutable and are passed in from a parent component. Components can manage their own state using the useState hook, or by using class-based components with the this.state method.

```javascript
import React, { useState } from 'react';

function Counter() {
  // useState is a hook which returns a pair: the current state value and a function that lets you update it
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

// class component version
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}
```





## Virtual DOM
JavaScript representation of the actual DOM improves performance by only re-rendering components that have changed
## Events
used to trigger changes in a component’s state
## Imports
in file importing a component, use `import` to import the component

```javascript
import MyComponent from './MyComponent';
```
in file defining component, use `export` to export the component

```javascript
import React, { Component } from 'react';

class MyComponent extends Component {
  render() {
    return (
      <div>
        MyComponent
      </div>
    );
  }
}

export default MyComponent;
```

## Lifecycle methods
allow developers to control when components are created and destroyed, and when they should be re-rendered. Lifecycle methods are only available in class components, not functional components as they do not have methods.
```javascript
import React, { Component } from 'react';

class ExampleComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      message: 'Hello World'
    };
  }

  componentDidMount() {
    fetch('https://example.com/api/message')
      .then(response => response.json())
      .then(data => {
        this.setState({
          message: data.message
        });
      });
  }

  componentDidUpdate(prevProps, prevState) {
    if (prevState.message !== this.state.message) {
      fetch('https://example.com/api/message')
        .then(response => response.json())
        .then(data => {
          this.setState({
            message: data.message
          });
        });
    }
  }

  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
}

export default ExampleComponent;
```
Functional Version using Hooks 
```
import React, { useState, useEffect } from 'react';

function ExampleComponent() {
  const [message, setMessage] = useState('Hello World');

  useEffect(() => {
    fetch('https://example.com/api/message')
      .then(response => response.json())
      .then(data => {
        setMessage(data.message);
      });
  }, []);

  return (
    <div>
      <h1>{message}</h1>
    </div>
  );
}

export default ExampleComponent;
```
## Context
allows developers to share data between components without passing props down manually. A consumer component subscribes to context changes, and a provider component provides changes using value prop.
### Context Provider
```
import React from 'react';
import { ColorContext } from './context';

export default function ColorProvider({ children }) {
  return (
    <ColorContext.Provider value="blue">
      {children}
    </ColorContext.Provider>
  );
}
```
### Context Consumer
```
import React, { useContext } from 'react';
import { ColorContext } from './context';

export default function ColorConsumer() {
  const color = useContext(ColorContext);
  return <p>The color is {color}</p>;
}
```
### Context (context.js)
```
import React from 'react';

export const ColorContext = React.createContext();
```

## Portals 
allow components to be rendered outside of the current DOM hierarchy.
An example of where this might be used is in a **modal**, which is a type of window used to display important information or provide a certain functionality, such as a dialog box or a form
```
import React from 'react';
import ReactDOM from 'react-dom';

function Modal({ children }) {
  return ReactDOM.createPortal(
    <div className="modal">
      {children}
    </div>,
    document.getElementById('modal')
  );
}

export default Modal;
```

## Refs
provide a way to access DOM nodes directly from React components.
## Fragments 
group multiple elements together without adding extra nodes to the DOM.
## Error boundaries
components that are used to catch errors in components, allowing the application to continue functioning.

## React Router
a library used to create routing in React applications
## Suspense 
enables components to suspend rendering until data is loaded, allowing for better performance.
## memo 
a higher-order component used to optimize performance by memoizing the component and re-rendering it only when necessary

## ReactDOM
`ReactDOM.render(<h1></h1>, document.getElementById('root'));`

# html/css
# javascript
document.createElement('h1');
h1.textContent
h1.className
document.getElementById

const element = <h1 classname="title">Hello World</h1>;
console.log(element);

ReactDOM.render(element, document.getElementById('root'));  
# three.js
# 3d force graph
# d3
# observable
# p5
# anime


