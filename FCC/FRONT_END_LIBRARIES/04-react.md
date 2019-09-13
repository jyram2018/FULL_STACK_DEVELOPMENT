# REACT

Note: The challenges are realised in FCC environment with the following syntax called:
```ReactDOM.render(JSX, document.getElementById('root'));```.

**1. React: Create a Simple JSX Element**
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
This is rarely needed but it's good to keep it in mind! Please consult the <a href = "https://reactjs.org/docs/state-and-lifecycle.html">React documentation</a> for further details.

```javascript
```
**25. **
```javascript
```
**26. **
```javascript
```
**27. **
```javascript
```
**28. **
```javascript
```
**29. **
```javascript
```
**30. **
```javascript
```
**31. **
```javascript
```
**32. **
```javascript
```
**33. **
```javascript
```
**34. **
```javascript
```
**35. **
```javascript
```
**36. **
```javascript
```
**37. **
```javascript
```
**38. **
```javascript
```
**39. **
```javascript
```
**40 **
```javascript
```
**41 **
```javascript
```
**42. **
```javascript
```
**43. **
```javascript
```
**44. **
```javascript
```
**45. **
```javascript
```
**46. **
```javascript
```
**47. **
```javascript
```
**48. **
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