# REACT AND REDUX

**1. React and Redux: Getting Started with React Redux**

This series of challenges introduces how to use Redux with React. First, here's a review of some of the key principles of each technology.

React is a view library that you provide with data, then it renders the view in an efficient, predictable way.

Redux is a state management framework that you can use to simplify the management of your application's state.

Typically, in a React Redux app, you create a single Redux store that manages the state of your entire app. Your React components subscribe to only the pieces of data in the store that are relevant to their role. Then, you dispatch actions directly from React components, which then trigger store updates.

Although React components can manage their own state locally, when you have a complex app, it's generally better to keep the app state in a single location with Redux. There are exceptions when individual components may have local state specific only to them.

Finally, because Redux is not designed to work with React out of the box, you need to use the ```react-redux``` package. It provides a way for you to pass Redux ```state``` and ```dispatch``` to your React components as ```props```.

Over the next few challenges:

First, you'll create a simple React component which allows you to input new text messages. These are added to an array that's displayed in the view. This should be a nice review of what you learned in the React lessons.

Next, you'll create a Redux store and actions that manage the state of the messages array.

Finally, you'll use ```react-redux``` to connect the Redux store with your component, thereby extracting the local state into the Redux store.

```javascript
class DisplayMessages extends React.Component {
  // change code below this line
  constructor(props) {
    super(props);
    this.state = {
      input: "",
      messages: []
    };
  }
  // change code above this line
  render() {
    return <div />
  }
};
```

**2. React and Redux: Manage State Locally First**

```javascript
class DisplayMessages extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: '',
      messages: []
    }
    this.handleChange = this.handleChange.bind(this)
    this.submitMessage = this.submitMessage.bind(this)
  }
  
  // add handleChange() and submitMessage() methods here
  handleChange(event) {
    this.setState({
      input : event.target.value
    });
  }
  submitMessage() {
    this.setState({
      input : "",
      messages: this.state.messages
        .concat(this.state.input)
    });
  }

  render() {
    return (
      <div>
        <h2>Type in a new Message:</h2>
        { /* render an input, button, and ul here */ }
          <input 
          onChange={this.handleChange}
          value={this.state.input}
          />
          <button onClick={this.submitMessage}>
          Click Me
          </button>
          <ul>
            {this.state.messages.map(
              (x) => <li>{x}</li>)}
          </ul>
        { /* change code above this line */ }
      </div>
    );
  }
};
```

**3. React and Redux: Extract State Logic to Redux**

Now that you finished the React component, you need to move the logic it's performing locally in its ```state``` into Redux.

This is the first step to connect the simple React app to Redux.

The only functionality your app has is to add new messages from the user to an unordered list.
The example is simple in order to demonstrate how React and Redux work together.

```javascript
// define ADD, addMessage(), messageReducer(), and store here:
const ADD = 'ADD';

const addMessage = (message) => {
  return {
    type : ADD,
    message
  }
};

const messageReducer = (state = [], action)=> {
  switch(action.type){
    case ADD:
      return state.concat(action.message)
    default:
      return state;
  }
};

const store = Redux.createStore(messageReducer);
```

**4. Use Provider to Connect Redux to React**

```javascript
```

```javascript
```

```javascript
```

```javascript
```

```javascript
```
