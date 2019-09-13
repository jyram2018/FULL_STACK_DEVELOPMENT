# REACT

Note: The challenges are realised in FCC environment with the following syntax called: ```ReactDOM.render(JSX, document.getElementById('root'));```.

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
