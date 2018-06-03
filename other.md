### Where exactly is the `React` import used in a React component?   
JSX (return value of render() method) compiles to `React.createElement(...)`.    

### What's the correct notation when importing a component?  
`Person.js`: // capital P is a just convention  
`export default person; // here by convention: use uppercase P for smart components and lowercase p for dumb (functional) components.`  
`X.js`:   
`import Person from 'path/to/Person.js'; // !!! for JSX to understand Person as a react component the capital letter is a must (even if the export is default so in a non-react context it can be named whatever).` 

### How is a react app architectured?  
A react app is typucally component tree:  
* one root component, the `App` component   
* a potentially infinite amount of nested child components.

### What's JSX?  
JSX is JS that looks like HTML. Compiled onto JS via Babel.  
JSX is just syntactic sugar for JavaScript, allowing to write HTMLish code instead of nested `React.createElement(...)` calls.  
E.g.:   
`return React.createElement("div", { className: "App" }, // ... and other nested calls for nested elements` 
becomes  
    `return (
      <div className="App">
        // nest elements normally just like in HTML
      </div>
    );`.  
    Much nicer.



### JSX constraints? 
* Only one parent (buyt not anymore actually)  
* Some words forbidden because they're JS, e.g. `class` (--> `className`) 

### What are two ways of creating a react component?  
**Dumb component (= stateless = functional = presentational)**  
`Person.js`:   
```javascript
import React from 'react';   
const person = (props) => {  
  return <div>{props.name}</div>;  
}  
export default person;
```   
Very simple about what it does: only renders something to the DOM. Dynamic thanks to props. <= Use functional components as often as possible, since they are simpler and don't manipulate app state.

**Smart component (= stateful = class-based = container)**   
`Person.js`:   
```javascript
import React, { Component } from 'react';   
class Person extens Component {  
  render() {
    return (<div>{this.props.name}</div>);  
  }
}  
export default Person;
```   

### What's the convention for a JSX file xtension?  
`.js`

### Props vs State?    
What they have in common:  
* Both props and state are JS objects.   
* Changes to props and state trigger an UI update (a targeted DOM updated after running diff algorithm against virtual DOM). More speciccally a change in the DOM happens only if one of these change.  

How they're different:  

Props = (JSX attributes) = passed from outside (i.e. from a parent=wrapping
component to a child=embedded component).   
Under the hood: props are custom JSX properties (HTML-attribute-like). 
E.g.: a card name should be a prop.   

State: managed inside. 
**Can be changed at runtime from within**. When the state changes, React checks whether to update the DOM.  
Under the hood: state is a class ppty of the `Component` class.
~~E.g.: a card state such as `active` or `inactive` should be a state.~~ // NO: in that case, `active` should be kept as **state** of the container component which anyhow already has a list of cards in its state. This way, we limit the number of states on the app.
NB:   
* The name `state` is mandatory.  
* State can only be manipulated by class-based components.  
* Functional components can read it but not manipulate it.

## What's a react component?  
A function that returns some JSX. 

## What does `this` refers to in a `class X extends Component`?  
To the class (that's just ES6). 

## About event handlers? 
Use ES6 arrow functions to keep the reference `this`--- this class, to be able to access state. 

## How to mutate the state? 
Use `this.setState()`.  
NOT NEEDED: `this.setState(Object.assign(this.state,...)`  
React already does that under the hood within `setState()`: the argument of `setState` gets merged with the
original state.  

## GOTCHAS  
* when a prop is not passed, it fails silently. Just nothing displayed or called.  

## How to keep a lower-level component stateless?  
* State remains in the container component  
* Keep the inner component functional  
* If an event from inside the functional component needs to change state, e.g. change its age:  
   * pass the handler (defined in the container component) to the inner component as a **prop**  
   * if need to pass arguments - for example if the state change relates to this inner component such as change own age - use **bind** :   
   `increaseAgeHandler={this.increaseAgeHandler.bind(this, this.state.persons[2])}`   
   Remember: bind createa a new function, it doesn't execute the function's inner code. 

