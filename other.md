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

### props vs state?   

props = a configuration (as a JS object, e.g. `{className: "app"}`).  
Stays the same at runtime.   
E.g.: a card name.  
(props = JSX attributes)

state: useful when need changes at runtime.  
E.g.: a card state such as "active" or "inactive". 

## What's a react component?  
A function that returns some JSX.
