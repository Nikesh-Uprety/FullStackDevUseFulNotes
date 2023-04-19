## React uses JSX which is Javascript in HTML in order the code to be executed the it must be compiled into JavaScript. 
## The transpiler Babel is a popular tool for this process.
# To render JSX in React
## `ReactDOM.render(JSX,document.getElementById('root'))`

## React Syntax to keep in Mind!
### `class should be replaced with className`
### All HTML attributes and events become `camelCase`
### `onclick event = onClick` `onchange=onChange`
# Write a React Component from Scratch
```javascript
class MyComponent extends React.Component {
constructor(props){
super(props)
}
  render() {
    return (
      <div>
        <h1>My First React Component!</h1>
      </div>
    );
  }
};

ReactDOM.render(<MyComponent/>,document.getElementById('root')) // 
```
# Pass an Array as Props
## We can pass the array with the same property with different values inside it to an components, and as the position of the component in the main app file it will display accordingly.
## Here is an example
```javascript
const List = (props) => {
  { /* Change code below this line */ }
  return <p>{props.tasks.join(", ")}</p>
  { /* Change code above this line */ }
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
        { /* Change code below this line */ }
        <List tasks={["walk dog", "workout"]}/>
        <h2>Tomorrow</h2>
        <List tasks={["walk dog", "workout","read a book"]}/>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```
# Use PropTypes to Define the Props You Expect
## Qn: Define `propTypes` for the `Items` component to require `quantity` as a prop and verify that it is of type `number`.
## Here is an quick example
```javascript
import PropTypes from 'prop-types';
// Change code below this line
Items.propTypes  = { quantity : PropTypes.number.isRequired}

// Change code above this line

Items.defaultProps = {
  quantity: 0
};
```

### Qn: The code editor has a `CampSite` component that renders a `Camper` component as a child. Define the `Camper` component and assign it default props of `{ name: 'CamperBot' }`. Inside the `Camper` component, render any code that you want, but make sure to have one `p` element that includes only the `name` value that is passed in as a `prop`. Finally, define `propTypes` on the `Camper` component to require `name` to be provided as a prop and verify that it is of type `string`.
 ```javascript 
 class CampSite extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <Camper name={'Nikesh'}/>
      </div>
    );
  }
};
// Change code below this line
class Camper extends React.Component {
  constructor(props) {
    super(props);
Camper.propTypes={ name : PropTypes.string.isRequired}
Camper.defaultProps={
  name:'CamperBot'
};

}
  render() {
    return (
      <div>
      <p>{this.props.name}</p>
      </div>
    );
  }
};
```
# Bind 'this' to a Class Method
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      text: "Hello"
    };
    // Change code below this line
     this.handleClick = this.handleClick.bind(this)
    // Change code above this line
  }
  handleClick() {
    this.setState({
      text: "You clicked!"
    });
  }
  render() {
    return (
      <div>
        { /* Change code below this line */ }
        <button onClick={this.handleClick}>Click Me</button>
        { /* Change code above this line */ }
        <h1>{this.state.text}</h1>
      </div>
    );
  }
};
```
# Add Inline Styles in React
#### For example,  the size of the font with `fontSize` instead of `font-size`. Hyphenated words like `font-size` are invalid syntax for JavaScript object properties, so React uses camel case. As a rule, any hyphenated style properties are written using camel case in JSX.
