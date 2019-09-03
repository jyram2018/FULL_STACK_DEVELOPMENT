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
** **
```javascript
```
** **
```javascript
```
** **
```javascript
```
