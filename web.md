# DOM
the DOM is a tree structure that represents the content of a web page. it is used to represent the structure of a document and allows programs and scripts to dynamically access and update

# HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Title</title>
  </head>
  <body>
    <h1>Heading</h1>
    <p>paragraph</p>
</html>
```

# CSS

```css
h1 {
  color: red;
  font-size: 5em;
}
```

# JavaScript

```js
document.getElementById("demo").innerHTML = "Hello";
```

# selenium

- Locating Elements: This is the process of finding elements on a web page using locators like id, name, class, XPath, CSS selector, etc. For example:
- Find element by id 
`element = driver.find_element_by_id("element_id")`

- Find element by XPath 
`element = driver.find_element_by_xpath("//div[@class='some-class']/a")`
User Interactions: This is the process of simulating user actions such as clicking, entering text, selecting options, etc. For example:
- Clicking an element 
`element.click()`

- Entering text in an input field 
`element.send_keys("some text")`

- Selecting an option from a dropdown list 
`element.select_by_value("some_value")`

- Waits: This is the process of waiting for a certain condition to be met before executing the next step. Examples include waiting for an element to be visible, waiting for an element to be clickable, etc. For example:
- Waiting for an element to be visible 
`WebDriverWait(driver, 10).until(EC.visibility_of_element_located((By.ID, "element_id")))`

- Waiting for an element to be clickable 
`WebDriverWait(driver, 10).until(EC.element_to_be_clickable((By.ID, "element_id")))`
- Assertions: This is the process of checking if a certain condition is met before continuing with the test. For example:
Asserting that an element's text is equal to a certain value 
`assert element.text == "some value"`

# chrome devtools
The Elements tab is used to inspect and analyze HTML, CSS, and JavaScript of a web page. It allows you to view the source code, inspect the DOM tree of a page, and make changes to the code in real-time.

The Console tab is used to debug and test JavaScript code. It allows you to view console output, view errors, and evaluate JavaScript expressions.

The Sources tab is used to debug and test JavaScript code. It allows you to view the source code, set breakpoints, and step through code execution.

The Network tab is used to analyze network performance and optimize network requests. It allows you to view and analyze HTTP requests, view headers and response data, and view WebSocket messages.

The Performance tab is used to measure the performance of web pages and applications. It allows you to view the timeline of page load events, analyze performance metrics, and identify potential performance issues.

The Application tab is used to inspect and analyze the security and privacy of a web page. It allows you to view and analyze cookies, view and modify local storage, and view security certificates.

# chrome extensions
a chrome extension has a manifest.json file that describes the extension and its components. The manifest.json file is required for all extensions, and must be in the root directory of the extension

a chrome extension can have a background script that runs in the background and can be used to perform tasks that don't require a user interface

a chrome extension can have a content script that runs on a web page and can be used to modify the page

a chrome extension can have a popup script that runs when the user clicks on the extension's icon in the toolbar

a chrome extension can have a options script that runs when the user clicks on the extension's options page

# php
```php
<?php
// PHP Basics
$variable = 'value';
echo $variable; // prints 'value'

// Arrays
$array = array(1, 2, 3);
echo $array[0]; // prints 1

// If Statements
if ($variable == 'value') {
    echo 'The variable is equal to value';
}

// Loops
for ($i=0; $i<10; $i++) {
    echo $i; // prints 0-9
}

// Functions
function myFunction($parameter) {
    return $parameter;
}

echo myFunction('Hello'); // prints 'Hello'

// Classes
class MyClass {
    public function __construct() {
        // do something
    }
}

$myClass = new MyClass();
?>
```


# express

```javascript
const express = require('express');

const app = express();

// middleware - to parse incoming json data
app.use(express.json());

// define routes
app.get('/', (req, res) => {
  res.status(200).send('Welcome to Express');
});

app.post('/contact', (req, res) => {
  const { name, email, message } = req.body;
  res.status(200).send(`Message from ${name}: ${message}`);
});

// start server
app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

# node
 The Node.js package ecosystem, npm, is the largest ecosystem of open source libraries in the world

- `npm init` to create package.json
- `npm install` to install dependencies
- `npm start` to run start script
- `npm test` to run test script
- `npm run` to run custom script
- `npm uninstall` to uninstall dependencies
- `npm update` to update dependencies
- `npm outdated` to check for outdated dependencies
- `npm audit` to check for vulnerabilities

a package.json file contains information about the project, such as the name, version, description, and dependencies

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "My project description",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "John Doe",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1"
  }
}
```



`npm -v` to check version



https://nodejs.org/en/download/

# react

## webpack

`npm install webpack webpack-cli --save-dev` to install webpack and webpack-cli

webpack allows you to use import and export within your code

you can import images directly into javascript files

## storybook

`npx storybook init` to create a new storybook

a story is the rendered state of one ui component




## sass

`npm install sass` to install sass

sass is a css preprocessor that allows you to use variables, nesting, mixins, and other features that don't exist in css

mixins are reusable pieces of css that can be used in multiple places

## create-react-app

`npx create-react-app my-app` to create a new react app
`

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

you can use unpkg.com to import a component from a CDN

`<script src="https://unpkg.com/react/umd/react.production.min.js" crossorigin></script>09-
`

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
```
document.createElement('h1');
h1.textContent
h1.className
document.getElementById

const element = <h1 classname="title">Hello World</h1>;
console.log(element);

ReactDOM.render(element, document.getElementById('root'));  
```
# three.js
# 3d force graph
# d3
# observable
# p5
# anime

# random

web socket is a communication protocol which provides full duplex communication channels over a single TCP connection. It was defined by the IETF in RFC 6455 in 2011