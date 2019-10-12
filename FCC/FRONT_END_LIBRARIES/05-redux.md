# REDUX

**1. Redux: Create a Redux Store**

Redux is a state management framework that can be used with a number of different web technologies, including React.

In Redux, there is a single state object that's responsible for the entire state of your application. This means if you had a React app with ten components, and each component had its own local state, the entire state of your app would be defined by a single state object housed in the Redux ```store```. This is the first important principle to understand when learning Redux: the Redux store is the single source of truth when it comes to application state.

This also means that any time any piece of your app wants to update state, it **must** do so through the Redux store. The unidirectional data flow makes it easier to track state management in your app.

```javascript
const reducer = (state = 5) => {
  return state;
}

// Redux methods are available from a Redux object
// For example: Redux.createStore()
// Define the store here:

var store = Redux.createStore(reducer);
```
**2. Redux: Get State from the Redux Store**
```javascript
const store = Redux.createStore(
  (state = 5) => state
);

// change code below this line
var currentState = store.getState();
```
**3. Redux: Define a Redux Action**

Since Redux is a state management framework, updating state is one of its core tasks. In Redux, all state updates are triggered by dispatching actions. An action is simply a JavaScript object that contains information about an action event that has occurred. The Redux store receives these action objects, then updates its state accordingly. Sometimes a Redux action also carries some data. For example, the action carries a username after a user logs in. While the data is optional, actions must carry a ```type``` property that specifies the 'type' of action that occurred.

Think of Redux actions as messengers that deliver information about events happening in your app to the Redux store. The store then conducts the business of updating state based on the action that occurred.

```javascript
// Define an action here:
const action = {type: 'LOGIN'};
```
**4. Redux: Define an Action Creator**

After creating an action, the next step is sending the action to the Redux store so it can update its state. In Redux, you define action creators to accomplish this. An action creator is simply a JavaScript function that returns an action. In other words, action creators create objects that represent action events.

```javascript
const action = {
  type: 'LOGIN'
}
// Define an action creator here:
const actionCreator = (action) => {
  return action
}
```
**5. Redux: Dispatch an Action Event**

```dispatch``` method is what you use to dispatch actions to the Redux store. Calling ```store.dispatch()``` and passing the value returned from an action creator sends an action back to the store.

Recall that action creators return an object with a type property that specifies the action that has occurred. Then the method dispatches an action object to the Redux store. Based on the previous challenge's example, the following lines are equivalent, and both dispatch the action of type ```LOGIN```:

    store.dispatch(actionCreator());
    store.dispatch({ type: 'LOGIN' });

```javascript
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

// Dispatch the action here:
store.dispatch(loginAction());
```
**6. Redux: Handle an Action in the Store**
After an action is created and dispatched, the Redux store needs to know how to respond to that action.
This is the job of a reducer function.
Reducers in Redux are responsible for the state modifications that take place in response to actions.
A reducer takes state and action as arguments, and it always returns a new state.

It is important to see that this is the **only** role of the reducer.
It has no side effects — it never calls an API endpoint and it never has any hidden surprises.
The reducer is simply a pure function that takes state and action, then returns new state.

Another key principle in Redux is that state is read-only.
In other words, the reducer function must always return a new copy of state and never modify state directly.
Redux does not enforce state immutability, however, you are responsible for enforcing it in the code of your reducer functions. You'll practice this in later challenges.

```javascript
const defaultState = {
  login: false
};

const reducer = (state = defaultState, action) => {
  // change code below this line
  return action.type == "LOGIN" ?
    {login: true} :
    state
  // change code above this line
};

const store = Redux.createStore(reducer);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};
```
**7. Redux: Use a Switch Statement to Handle Multiple Actions**

You can tell the Redux store how to handle multiple action types.
Say you are managing user authentication in your Redux store.
You want to have a state representation for when users are logged in and when they are logged out.
You represent this with a single state object with the property ```authenticated```.
You also need action creators that create actions corresponding to user login and user logout, along with the action objects themselves.

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
