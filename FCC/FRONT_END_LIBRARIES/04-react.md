# REACT

Note: The challenges are realised in FCC environment with the following syntax called:
```
ReactDOM.render(JSX, document.getElementById('root'));
```

**1. React: Create a Simple JSX Element**

**Intro**: React is an Open Source view library created and maintained by Facebook.
It's a great tool to render the User Interface (UI) of modern web applications.

React uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript.
Because JSX is a syntactic extension of JavaScript, you can actually write JavaScript directly within JSX.
To do this, you simply include the code you want to be treated as JavaScript within curly braces: 
```
{ 'this is treated as JavaScript code' }
```
However, because JSX is not valid JavaScript, JSX code must be compiled into JavaScript.
The transpiler Babel is a popular tool for this process.
It's already added behind the scenes for these challenges. 
It's worth noting that under the hood the challenges are calling
```
ReactDOM.render(JSX, document.getElementById('root'));
```
This function call is what places your JSX into React's own lightweight representation of the DOM.
React then uses snapshots of its own DOM to optimize updating only specific parts of the actual DOM.

```javascript
const JSX = <h1>Hello JSX!</h1>;
```
**2. React: Create a Complex JSX Element**
```javascript
const JSX = (
  <div>
    <h1>Hello</h1>
    <p>Some text</p>
    <ul>
      <li>A</li>
      <li>B</li>
      <li>C</li>
    </ul>
  </div>
);
```
**3. React: Add Comments in JSX**
```javascript
const JSX = (
  <div>
    {/*Comment*/}
    <h1>This is a block of JSX</h1>
    <p>Here's a subtitle</p>
  </div>
);
```
**4. React: Render HTML Elements to the DOM**

```ReactDOM.render()``` must be called after the JSX element declarations,
just like how you must declare variables before using them.
The code editor has a simple JSX component.
Use the ```ReactDOM.render()``` method to render this component to the page.
You can pass defined JSX elements directly in as the first argument
and use ```document.getElementById()``` to select the DOM node to render them to.
There is a div with ```id='challenge-node'``` available for you to use.

```javascript
const JSX = (
  <div>
    <h1>Hello World</h1>
    <p>Lets render this to the DOM</p>
  </div>
);
// change code below this line
ReactDOM.render(JSX, document.getElementById("challenge-node"))
```
**5. React: Define an HTML Class in JSX**
```javascript
const JSX = (
  <div className="myDiv">
    <h1>Add a class to this div</h1>
  </div>
);
```
**6. React: Learn About Self-Closing JSX Tags**
```javascript
const JSX = (
  <div>
    <h2>Welcome to React!</h2> <br />
    <p>Be sure to close all tags!</p>
    <hr />
  </div>
);
```
**7. React: Create a Stateless Functional Component**
```javascript
const MyComponent = function() {
  // change code below this line
  return (
    <div>
      Hello
    </div>
  );
  // change code above this line
}
```
**8. React: Create a React Component**

The constructor is a special method used during the initialization of objects that are created with the class keyword.
It is best practice to call a component's constructor with super, and pass props to both.
This makes sure the component is initialized properly.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    // change code below this line
    return (
      <div>
        <h1>
          Hello React!
        </h1>
      </div>
    );
    // change code above this line
  }
};
```
**9. React: Create a Component with Composition**

When React encounters a custom HTML tag that references another component 
(a component name wrapped in < /> like in this example), 
it renders the markup for that component in the location of the tag. 

```javascript
const ChildComponent = () => {
  return (
    <div>
      <p>I am the child</p>
    </div>
  );
};

class ParentComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>I am the parent</h1>
        { /* change code below this line */ }
        <ChildComponent />

        { /* change code above this line */ }
      </div>
    );
  }
};
```
**10. React: Use React to Render Nested Components**
```javascript
const TypesOfFruit = () => {
  return (
    <div>
      <h2>Fruits:</h2>
      <ul>
        <li>Apples</li>
        <li>Blueberries</li>
        <li>Strawberries</li>
        <li>Bananas</li>
      </ul>
    </div>
  );
};

const Fruits = () => {
  return (
    <div>
      { /* change code below this line */ }
      <TypesOfFruit/>
      { /* change code above this line */ }
    </div>
  );
};

class TypesOfFood extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        { /* change code below this line */ }
        <Fruits/>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**11. React: Compose React Components**
```javascript
class Fruits extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h2>Fruits:</h2>
        { /* change code below this line */ }
        <NonCitrus/>;
        <Citrus/>;
         { /* change code above this line */ }
      </div>
    );
  }
};

class TypesOfFood extends React.Component {
  constructor(props) {
     super(props);
  }
  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        { /* change code below this line */ }
        <Fruits/>
        { /* change code above this line */ }
        <Vegetables />
      </div>
    );
  }
};
```
**12. React: Render a Class Component to the DOM**

The past few challenges focused on components and composition, so the rendering was done for you behind the scenes. However, none of the React code you write will render to the DOM without making a call to the ReactDOM API.

Here's a refresher on the syntax: ```ReactDOM.render(componentToRender, targetNode)```.
The first argument is the React component that you want to render.
The second argument is the DOM node that you want to render that component within.

React components are passed into ```ReactDOM.render()``` a little differently than JSX elements.
For JSX elements, you pass in the name of the element that you want to render.
However, for React components, you need to use the same syntax as if you were rendering a nested component, for example ```ReactDOM.render(<ComponentToRender />, targetNode)```.

```javascript

class TypesOfFood extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        {/* change code below this line */}
        <Fruits/>
        <Vegetables/>
        {/* change code above this line */}
      </div>
    );
  }
};

// change code below this line
ReactDOM.render(<TypesOfFood/>, document.getElementById('challenge-node'));
```
**13. React: Write a React Component from Scratch**

A typical React component is an ES6 class which extends React.Component.
It has a render method that returns HTML (from JSX) or null.
This is the basic form of a React component.

```javascript
// change code below this line
class MyComponent extends React.Component {
  constructor(props) {
    super(props)
  }
  render () {
    return (
      <div>
        <h1>My First React Component!</h1>
      </div>
    )
  }
}
ReactDOM.render(<MyComponent/>, document.getElementById('challenge-node'));
```
**14. React: Pass Props to a Stateless Functional Component**
```javascript

const CurrentDate = (props) => {
  return (
    <div>
      { /* change code below this line */ }
      <p>The current date is: {props.date} </p>
      { /* change code above this line */ }
    </div>
  );
};

class Calendar extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h3>What date is it?</h3>
        { /* change code below this line */ }
        <CurrentDate date={Date()}/>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**15. React: Pass an Array as Props**
```javascript
const List= (props) => {
  { /* change code below this line */ }
  return <p>{props.tasks.join(", ")}</p>
  { /* change code above this line */ }
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        { /* change code below this line */ }
        <List tasks = {["walk dog", "workout"]}/>
        <h2>Tomorrow</h2>
        <List tasks = {["walk dog", "workout", "shooping"]}/>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**16. React: Use Default Props**
```javascript
const ShoppingCart = (props) => {
  return (
    <div>
      <h1>Shopping Cart Component</h1>
    </div>
  )
};
// change code below this line
ShoppingCart.defaultProps = { items: 0 }
```
**17. React: Override Default Props**
```javascript
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
}

Items.defaultProps = {
  quantity: 0
}

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    { /* change code below this line */ }
    return <Items quantity = {10}/>
    { /* change code above this line */ }
  }
};
```
**18. React: Use PropTypes to Define the Props You Expect**

React provides useful type-checking features to verify that components receive props of the correct type.
For example, your application makes an API call to retrieve data that you expect to be in an array, which is then passed to a component as a prop. 

Note: As of React v15.5.0, PropTypes is imported independently from React, like this:

```import React, { PropTypes } from 'react';```

```javascript
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
};

// change code below this line
Items.propTypes = {
  quantity: PropTypes.number.isRequired
};
// change code above this line

Items.defaultProps = {
  quantity: 0
};

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <Items />
  }
};
```
**19. React: Access Props Using this.props**

Anytime you refer to a class component within itself, you use the this keyword.
To access props within a class component, you preface the code that you use to access it with this.
For example, if an ES6 class component has a prop called data, you write ```{this.props.data}``` in JSX.

```javascript
class ReturnTempPassword extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
            { /* change code below this line */ }
            <p>Your temporary password is: <strong>{this.props.tempPassword}</strong></p>
            { /* change code above this line */ }
        </div>
    );
  }
};

class ResetPassword extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
          <h2>Reset Password</h2>
          <h3>We have generated a new temporary password for you.</h3>
          <h3>Please reset this password from your account settings ASAP.</h3>
          { /* change code below this line */ }
          <ReturnTempPassword tempPassword = {"lolololol"}/>
          { /* change code above this line */ }
        </div>
    );
  }
};
```
**20. React: Review Using Props with Stateless Functional Components**

A stateless functional component is any function you write which accepts props and returns JSX.
A stateless component, on the other hand, is a class that extends ```React.Component```,
but does not use internal state (covered in the next challenge).
Finally, a stateful component is any component that does maintain its own internal state.
You may see stateful components referred to simply as components or React components.

A common pattern is to try to minimize statefulness and to create stateless functional components wherever possible.
This helps contain your state management to a specific area of your application.
In turn, this improves development and maintenance of your app by making it easier to follow how changes to state affect its behavior.

```javascript
class CampSite extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <Camper/>
      </div>
    );
  }
};
// change code below this line
class Camper extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <p>
        {this.props.name}
      </p>
    )
  }
}

Camper.defaultProps = {
  name: 'CamperBot'
};

Camper.propTypes = {
  name: PropTypes.string.isRequired
};
```
**21. React: Create a Stateful Component**

State consists of any data your application needs to know about, that can change over time.
You want your apps to respond to state changes and present an updated UI when necessary.

You create state in a React component by declaring a ```state``` property on the component class in its ```constructor```.
This initializes the component with ```state``` when it is created.
The ```state``` property must be set to a JavaScript ```object```. Declaring it looks like this:
```
this.state = {
  // describe your state here
}
```
You have access to the ```state``` object throughout the life of your component.
You can update it, render it in your UI, and pass it as props to child components.
The ```state``` object can be as complex or as simple as you need it to be.
Note that you must create a class component by extending ```React.Component``` in order to create ```state``` like this.
```javascript
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    // initialize state here
    this.state = {name: "jyram"};
  }
  render() {
    return (
      <div>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```
**22. React: Render State in the User Interface**

Note that if you make a component stateful, no other components are aware of its ```state```.
Its ```state``` is completely encapsulated, or local to that component, unless you pass state data to a child component as ```props```.
This notion of encapsulated ```state``` is very important because it allows you to write certain logic, then have that logic contained and isolated in one place in your code.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    return (
      <div>
        { /* change code below this line */ }
        <h1>{this.state.name}</h1>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**23. React: Render State in the User Interface Another Way**

There is another way to access ```state``` in a component.
In the ```render()``` method, before the ```return``` statement, you can write JavaScript directly.
For example, you could declare functions, access data from ```state``` or ```props```, perform computations on this data, and so on. Then, you can assign any data to variables, which you have access to in the ```return``` statement.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // change code below this line
    const name = this.state.name;
    // change code above this line
    return (
      <div>
        { /* change code below this line */ }
        <h1>{name}</h1>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**24. React: Set State with this.setState**

React provides a method for updating component ```state``` called ```setState```.
You call the ```setState``` method within your component class like so: ```this.setState()```, 
passing in an object with key-value pairs.
The keys are your state properties and the values are the updated state data.
For instance, if we were storing a ```username``` in state and wanted to update it, it would look like this:
```
this.setState({
  username: 'Lewis'
});
```
React expects you to never modify ```state``` directly, instead always use ```this.setState()``` when state changes occur.
Also, you should note that React may batch multiple ```state``` updates in order to improve performance.
What this means is that ```state``` updates through the ```setState``` method can be asynchronous.
There is an alternative syntax for the ```setState``` method which provides a way around this problem.
This is rarely needed but it's good to keep it in mind! Please consult the [React documentation](https://reactjs.org/docs/state-and-lifecycle.html) for further details.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'Initial State'
    };
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    // change code below this line
    this.setState({
      name : "React Rocks!"
    });
    // change code above this line
  }
  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me</button>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```
**25. React: Bind 'this' to a Class Method**

In addition to setting and updating ```state```, you can also define methods for your component class.
A class method typically needs to use the ```this``` keyword so it can access properties on the class (such as ```state``` and ```props```) inside the scope of the method.
There are a few ways to allow your class methods to access ```this```.

One common way is to explicitly bind ```this``` in the constructor so ```this``` becomes bound to the class methods when the component is initialized.
You may have noticed the last challenge used ```this.handleClick = this.handleClick.bind(this)``` for its ```handleClick``` method in the constructor.
Then, when you call a function like ```this.setState()``` within your class method, this refers to the class and will not be ```undefined```.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      itemCount: 0
    };
    // change code below this line
    this.addItem = this.addItem.bind(this)
    // change code above this line
  }
  addItem() {
    this.setState({
      itemCount: this.state.itemCount + 1
    });
  }
  render() {
    return (
      <div>
        { /* change code below this line */ }
        <button onClick = {this.addItem}>Click Me</button>
        { /* change code above this line */ }
        <h1>Current Item Count: {this.state.itemCount}</h1>
      </div>
    );
  }
};
```
**26. React: Use State to Toggle an Element**

You can use ```state``` in React applications in more complex ways than what you've seen so far.
One example is to monitor the status of a value, then render the UI conditionally based on this value.
There are several different ways to accomplish this, and the code editor shows one method.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      visibility: false
    };
    // change code below this line
    this.toggleVisibility = this.toggleVisibility.bind(this)
    // change code above this line
  }
  // change code below this line
  toggleVisibility() {
    this.setState({
      visibility: !this.state.visibility
    })
  }
  // change code above this line
  render() {
    if (this.state.visibility) {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
          <h1>Now you see me!</h1>
        </div>
      );
    } else {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
        </div>
      );
    }
  }
};
```
**27. <ins>React: Write a Simple Counter</ins>**

You can design a more complex stateful component by combining the concepts covered so far.
These include: 
  - initializing ```state```,
  - writing methods that set ```state```, and
  - assigning click handlers to trigger these methods.

```javascript
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
    // change code below this line
    this.increment = this.increment.bind(this);
    this.decrement = this.decrement.bind(this);
    this.reset = this.reset.bind(this);
    // change code above this line
  }
  // change code below this line
  increment() {
    this.setState({
      count: this.state.count + 1
    })
  }
  decrement() {
    this.setState({
      count: this.state.count - 1
    })
  }
  reset() {
    this.setState({
      count: 0
    })
  }
  // change code above this line
  render() {
    return (
      <div>
        <button className='inc' onClick={this.increment}>Increment!</button>
        <button className='dec' onClick={this.decrement}>Decrement!</button>
        <button className='reset' onClick={this.reset}>Reset</button>
        <h1>Current Count: {this.state.count}</h1>
      </div>
    );
  }
};
```
**28. <ins>React: Create a Controlled Input</ins>**

Your application may have more complex interactions between ```state``` and the rendered UI.
For example, form control elements for text input, such as ```input``` and ```textarea```, maintain their own state in the DOM as the user types.

With React, you can move this mutable state into a React component's ```state```.
The user's input becomes part of the application ```state```, so React controls the value of that input field.
Typically, if you have React components with input fields the user can type into, it will be a controlled input form.

```javascript
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    // change code below this line
    this.handleChange = this.handleChange.bind(this)
    // change code above this line
  }
  // change code below this line
  handleChange(event) {
    this.setState({
      input: event.target.value
    })
  }
  // change code above this line
  render() {
    return (
      <div>
        { /* change code below this line */}
        <input
          value = {this.state.input}
          onChange = {this.handleChange} />
        { /* change code above this line */}
        <h4>Controlled Input:</h4>
        <p>{this.state.input}</p>
      </div>
    );
  }
};
```
**29. <ins>React: Create a Controlled Form</ins>**

The last challenge showed that React can control the internal state for certain elements like input and textarea, which makes them controlled components. This applies to other form elements as well, including the regular HTML form element.

```javascript
class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: '',
      submit: ''
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event) {
    this.setState({
      input: event.target.value
    });
  }
  handleSubmit(event) {
    // change code below this line
    this.setState({
      submit: this.state.input
    });
    event.preventDefault();
    // change code above this line
  }
  render() {
    return (
      <div>
        <form onSubmit={this.handleSubmit}>
          { /* change code below this line */ }
          <input
            value = {this.state.input}
            onChange = {this.handleChange}/>
          { /* change code above this line */ }
          <button type='submit'>Submit!</button>
        </form>
        { /* change code below this line */ }
        <h1>{this.state.submit}</h1>
        { /* change code above this line */ }
      </div>
    );
  }
};
```
**30. React: Pass State as Props to Child Components**
```javascript
class MyApp extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'CamperBot'
    }
  }
  render() {
    return (
       <div>
         <Navbar name = {this.state.name} />
       </div>
    );
  }
};

class Navbar extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
    <div>
      <h1>Hello, my name is: {this.props.name} </h1>
    </div>
    );
  }
};
```
**31. React: Pass a Callback as Props**
```javascript
class MyApp extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      inputValue: ''
    }
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(event) {
    this.setState({
      inputValue: event.target.value
    });
  }
  render() {
    return (
       <div>
        { /* change code below this line */ }
        <GetInput
          input = {this.state.inputValue}
          handleChange = {this.handleChange} />
        <RenderInput
          input = {this.state.inputValue}
          />
        { /* change code above this line */ }
       </div>
    );
  }
};

class GetInput extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h3>Get Input:</h3>
        <input
          value={this.props.input}
          onChange={this.props.handleChange}/>
      </div>
    );
  }
};

class RenderInput extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h3>Input Render:</h3>
        <p>{this.props.input}</p>
      </div>
    );
  }
};
```
**32. React: Use the Lifecycle Method componentWillMount**

React components have several special methods that provide opportunities to perform actions at specific points in the lifecycle of a component.
These are called lifecycle methods, or lifecycle hooks, and allow you to catch components at certain points in time.
This can be:
  - before they are rendered,
  - before they update,
  - before they receive props,
  - before they unmount, and so on.
  
Here is a list of some of the main lifecycle methods.

```componentWillMount()``` is called before the ```render()``` method when a component is being mounted to the DOM.

```componentDidMount()``` is called after a component is mounted to the DOM.

```componentWillReceiveProps()``` is called whenever a component is receiving new props. 

```shouldComponentUpdate()```

```componentWillUpdate()```

```componentDidUpdate()``` is called immediately after a component re-renders.

```componentWillUnmount()```

Below a React Component Lifecycle Visual.

![React Component Lifecycle Visual](https://cdn-images-1.medium.com/max/2000/1*sn-ftowp0_VVRbeUAFECMA.png)

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  componentWillMount() {
    // change code below this line
    console.log("Hello")
    // change code above this line
  }
  render() {
    return <div />
  }
};
```
**33. React: Use the Lifecycle Method componentDidMount**

Most web developers, at some point, need to call an API endpoint to retrieve data. If you're working with React, it's important to know where to perform this action.

The best practice with React is to place API calls or any calls to your server in the lifecycle method ```componentDidMount()```. This method is called after a component is mounted to the DOM.
Any calls to ```setState()``` here will trigger a re-rendering of your component. When you call an API in this method, and set your state with the data that the API returns, it will automatically trigger an update once you receive the data.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      activeUsers: null
    };
  }
  componentDidMount() {
    setTimeout( () => {
      this.setState({
        activeUsers: 1273
      });
    }, 2500);
  }
  render() {
    return (
      <div>
        <h1>Active Users: { this.state.activeUsers }</h1>
      </div>
    );
  }
};
```
**34. React: Add Event Listeners**

The ```componentDidMount()``` method is also the best place to attach any event listeners you need to add for specific functionality. React provides a synthetic event system which wraps the native event system present in browsers. This means that the synthetic event system behaves exactly the same regardless of the user's browser - even if the native events may behave differently between different browsers.

You've already been using some of these synthetic event handlers such as ```onClick()```. React's synthetic event system is great to use for most interactions you'll manage on DOM elements. However, if you want to attach an event handler to the document or window objects, you have to do this directly.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      message: ''
    };
    this.handleEnter = this.handleEnter.bind(this);
    this.handleKeyPress = this.handleKeyPress.bind(this);
  }
  // change code below this line
  componentDidMount() {
    document.addEventListener("keydown", this.handleKeyPress)
  }
  componentWillUnmount() {
    document.removeEventListener("keydown", this.handleKeyPress)
  }
  // change code above this line
  handleEnter() {
    this.setState({
      message: this.state.message + 'You pressed the enter key! '
    });
  }
  handleKeyPress(event) {
    if (event.keyCode === 13) {
      this.handleEnter();
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
};
```
**35. React: Manage Updates with Lifecycle Methods**

Another lifecycle method is ```componentWillReceiveProps()``` which is called whenever a component is receiving new props.
This method receives the new props as an argument, which is usually written as ```nextProps```.
You can use this argument and compare with ```this.props``` and perform actions before the component updates.
For example, you may call ```setState()``` locally before the update is processed.

Another method is ```componentDidUpdate()```, and is called immediately after a component re-renders. Note that rendering and mounting are considered different things in the component lifecycle.
When a page first loads, all components are mounted and this is where methods like ```componentWillMount()``` and ```componentDidMount()``` are called.
After this, as state changes, components re-render themselves.
The next challenge covers this in more detail.

```javascript
class Dialog extends React.Component {
  constructor(props) {
    super(props);
  }
  componentWillUpdate() {
    console.log('Component is about to update...');
  }
  // change code below this line
  componentWillReceiveProps(nextProps) {
    console.log(this.props);
    console.log(nextProps)
  }
  componentDidUpdate() {
    console.log("Component has updated.")
  }
  // change code above this line
  render() {
    return <h1>{this.props.message}</h1>
  }
};

class Controller extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      message: 'First Message'
    };
    this.changeMessage = this.changeMessage.bind(this);
  }
  changeMessage() {
    this.setState({
      message: 'Second Message'
    });
  }
  render() {
    return (
      <div>
        <button onClick={this.changeMessage}>Update</button>
        <Dialog message={this.state.message}/>
      </div>
    );
  }
};
```
**36. React: Optimize Re-Renders with shouldComponentUpdate**

So far, if any component receives new ```state``` or new ```props```, it re-renders itself and all its children. This is usually okay.
But React provides a lifecycle method you can call when child components receive new ```state``` or ```props```, and declare specifically if the components should update or not.
The method is ```shouldComponentUpdate()```, and it takes ```nextProps``` and ```nextState``` as parameters.

This method is a useful way to optimize performance.
For example, the default behavior is that your component re-renders when it receives new ```props```, even if the ```props``` haven't changed.
You can use ```shouldComponentUpdate()``` to prevent this by comparing the ```props```.
The method must return a boolean value that tells React whether or not to update the component.
You can compare the current props (```this.props```) to the next props (```nextProps```) to determine if you need to update or not, and return ```true``` or ```false``` accordingly.

```javascript
class OnlyEvens extends React.Component {
  constructor(props) {
    super(props);
  }
  shouldComponentUpdate(nextProps, nextState) {
    console.log('Should I update?');
     // change code below this line
    return nextProps.value % 2 == 0 ? true : false;
     // change code above this line
  }
  componentWillReceiveProps(nextProps) {
    console.log('Receiving new props...');
  }
  componentDidUpdate() {
    console.log('Component re-rendered.');
  }
  render() {
    return <h1>{this.props.value}</h1>
  }
};

class Controller extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: 0
    };
    this.addValue = this.addValue.bind(this);
  }
  addValue() {
    this.setState({
      value: this.state.value + 1
    });
  }
  render() {
    return (
      <div>
        <button onClick={this.addValue}>Add</button>
        <OnlyEvens value={this.state.value}/>
      </div>
    );
  }
};
```
**37. React: Introducing Inline Styles**

JSX elements use the ```style``` attribute, but because of the way JSX is transpiled, you can't set the value to a ```string```.
Instead, you set it equal to a JavaScript ```object```. Here's an example:

```<div style={{color: "yellow", fontSize: 16}}>Mellow Yellow</div>```

Notice how we camelCase the "fontSize" property?
This is because React will not accept kebab-case keys in the style object. React will apply the correct property name for us in the HTML.

```javascript

class Colorful extends React.Component {
  render() {
    return (
      <div style = {{
        color: "red",
        fontSize: 72
      }}>
        Big Red
      </div>
    );
  }
};

```
**38. React: Add Inline Styles in React**
```javascript
const styles = {
  color:"purple",
  fontSize: 40,
  border: "2px solid purple"
}
// change code above this line
class Colorful extends React.Component {
  render() {
    // change code below this line
    return (
      <div style={styles}>Style Me!</div>
    );
    // change code above this line
  }
};

```
**39. React: Use Advanced JavaScript in React Render Method**
```javascript
const inputStyle = {
  width: 235,
  margin: 5
}

class MagicEightBall extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      userInput: '',
      randomIndex: ''
    }
    this.ask = this.ask.bind(this);
    this.handleChange = this.handleChange.bind(this);
  }
  ask() {
    if (this.state.userInput) {
      this.setState({
        randomIndex: Math.floor(Math.random() * 20),
        userInput: ''
      });
    }
  }
  handleChange(event) {
    this.setState({
      userInput: event.target.value
    });
  }
  render() {
    const possibleAnswers = [
      'It is certain',
      'It is decidedly so',
      'Without a doubt', 
      'Yes, definitely',
      'You may rely on it',
      'As I see it, yes',
      'Outlook good',
      'Yes',
      'Signs point to yes',
      'Reply hazy try again',
      'Ask again later',
      'Better not tell you now',
      'Cannot predict now',
      'Concentrate and ask again',
      'Don\'t count on it', 
      'My reply is no',
      'My sources say no',
      'Most likely',
      'Outlook not so good',
      'Very doubtful'
    ];
    const answer = possibleAnswers[this.state.randomIndex] // << change code here
    return (
      <div>
        <input
          type="text"
          value={this.state.userInput}
          onChange={this.handleChange}
          style={inputStyle} /><br />
        <button onClick={this.ask}>
          Ask the Magic Eight Ball!
        </button><br />
        <h3>Answer:</h3>
        <p>
          { /* change code below this line */ }
          {answer}
          { /* change code above this line */ }
        </p>
      </div>
    );
  }
};
```
**40. React: Render with an If/Else Condition**
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      display: true
    }
    this.toggleDisplay = this.toggleDisplay.bind(this);
  }
  toggleDisplay() {
    this.setState({
      display: !this.state.display
    });
  }
  render() {
    // change code below this line
    if (this.state.display) {
          return (
      <div>
        <button onClick={this.toggleDisplay}>
          Toggle Display
        </button>
        <h1>Displayed!</h1>
      </div>
      );
    }
    else {
          return (
      <div>
        <button onClick={this.toggleDisplay}>
          Toggle Display</button>
      </div>
    );
    }
  }
};
```
**41. React: Use && for a More Concise Conditional**
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      display: true
    }
    this.toggleDisplay = this.toggleDisplay.bind(this);
  }
  toggleDisplay() {
    this.setState({
      display: !this.state.display
    });
  }
  render() {
    // change code below this line
    return (
      <div>
        <button onClick={this.toggleDisplay}>
          Toggle Display
        </button>
        {this.state.display &&<h1>Displayed!</h1>}
      </div>
    );
  }
};
```
**42. React: Use a Ternary Expression for Conditional Rendering**
```javascript

const inputStyle = {
  width: 235,
  margin: 5
}

class CheckUserAge extends React.Component {
  constructor(props) {
    super(props);
    // change code below this line
    this.state = {
      input: "",
      userAge: ""
    }
    // change code above this line
    this.submit = this.submit.bind(this);
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(e) {
    this.setState({
      input: e.target.value,
      userAge: ''
    });
  }
  submit() {
    this.setState({
      userAge: this.state.input
    });
  }
  render() {
    const buttonOne = <button onClick={this.submit}>Submit</button>;
    const buttonTwo = <button>You May Enter</button>;
    const buttonThree = <button>You Shall Not Pass</button>;
    return (
      <div>
        <h3>Enter Your Age to Continue</h3>
        <input
          style={inputStyle}
          type="number"
          value={this.state.input}
          onChange={this.handleChange} /><br />
        {
          !this.state.userAge ?
          buttonOne :
            this.state.userAge < 18 ?
            buttonThree :
            buttonTwo
        }
      </div>
    );
  }
};
```
**43. <ins>React: Render Conditionally from Props</ins>**
```javascript
class Results extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <h1>
      {
        this.props.fiftyFifty ?
        "You win!" : "You lose!"
      }
      </h1>
    )
  };
};

class GameOfChance extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 1
    }
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({
      counter: this.state.counter + 1 // change code here
    });
  }
  render() {
    let expression = Math.random() > .5; // change code here
    return (
      <div>
        <button onClick={this.handleClick}>Play Again</button>
        { /* change code below this line */ }
        <Results fiftyFifty = {expression}/>
        { /* change code above this line */ }
        <p>{'Turn: ' + this.state.counter}</p>
      </div>
    );
  }
};
```
**44. React: Change Inline CSS Conditionally Based on Component State**
```javascript

class GateKeeper extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(event) {
    this.setState({ input: event.target.value })
  }
  render() {
    let inputStyle = {
      border: '1px solid black'
    };
    // change code below this line
    this.state.input.length > 15 ?
    inputStyle.border = "3px solid red" : ""
    // change code above this line
    return (
      <div>
        <h3>Don't Type Too Much:</h3>
        <input
          type="text"
          style={inputStyle}
          value={this.state.input}
          onChange={this.handleChange} />
      </div>
    );
  }
};
```
**45. <ins>React: Use Array.map() to Dynamically Render Elements</ins>**
```javascript
const textAreaStyles = {
  width: 235,
  margin: 5
};

class MyToDoList extends React.Component {
  constructor(props) {
    super(props);
    // change code below this line
    this.state = {
      userInput: "",
      toDoList: []
    }
    // change code above this line
    this.handleSubmit = this.handleSubmit.bind(this);
    this.handleChange = this.handleChange.bind(this);
  }
  handleSubmit() {
    const itemsArray = this.state.userInput.split(',');
    this.setState({
      toDoList: itemsArray
    });
  }
  handleChange(e) {
    this.setState({
      userInput: e.target.value
    });
  }
  render() {
    const items = this.state.toDoList.map(
      x => <li>{x}</li>
    )
    return (
      <div>
        <textarea
          onChange={this.handleChange}
          value={this.state.userInput}
          style={textAreaStyles}
          placeholder="Separate Items With Commas" /><br />
        <button onClick={this.handleSubmit}>Create List</button>
        <h1>My "To Do" List:</h1>
        <ul>
          {items}
        </ul>
      </div>
    );
  }
};
```
**46. React: Give Sibling Elements a Unique Key Attribute**

When you create an array of elements, each one needs a ```key``` attribute set to a unique value.
React uses these keys to keep track of which items are added, changed, or removed.
This helps make the re-rendering process more efficient when the list is modified in any way.
Note that keys only need to be unique between sibling elements, they don't need to be globally unique in your application.

```javascript

const frontEndFrameworks = [
  'React',
  'Angular',
  'Ember',
  'Knockout',
  'Backbone',
  'Vue'
];

function Frameworks() {
  const renderFrameworks = frontEndFrameworks.map(
    (x, y) => <li key = {y + x}>{x}</li>
  ); // change code here
  return (
    <div>
      <h1>Popular Front End JavaScript Frameworks</h1>
      <ul>
        {renderFrameworks}
      </ul>
    </div>
  );
};
```
**47. <ins>React: Use Array.filter() to Dynamically Filter an Array</ins>**
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      users: [
        {
          username: 'Jeff',
          online: true
        },
        {
          username: 'Alan',
          online: false
        },
        {
          username: 'Mary',
          online: true
        },
        {
          username: 'Jim',
          online: false
        },
        {
          username: 'Sara',
          online: true
        },
        {
          username: 'Laura',
          online: true
        }
      ]
    }
  }
  render() {
    const usersOnline = this.state.users.filter(
      x => x.online == true
    ); // change code here
    const renderOnline = usersOnline.map(
      (x, y) => <li key = {y + x.username}>{x.username}</li>
    ); // change code here
    return (
       <div>
         <h1>Current Online Users:</h1>
         <ul>
           {renderOnline}
         </ul>
       </div>
    );
  }
};
```
**48. React: Render React on the Server with renderToString**
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
