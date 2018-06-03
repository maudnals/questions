### Where exactly is the `React` import used in a React component?   
JSX (return value of render() method) compiles to `React.createElement(...)`.    

### What's the correct notation when importing a component?  
`Person.js`: // capital P is a just convention  
`export default person; // here by convention: use uppercase P for smart components and lowercase p for dumb (functional) components.`  
`X.js`:   
`import Person from 'path/to/Person.js'; // !!! for JSX to understand Person as a react component the capital letter is a must (even if the export is default so in a non-react context it can be named whatever).` 



### What's JSX?  
JSX is JS that looks like HTML. Compiled onto JS via Babel.  
JSX is just syntactic sugar for JavaScript, allowing to write HTMLish code instead of nested `React.createElement(...)` calls.

### What are two ways of creating a react component?  
**Dumb component (no state)**  
`Person.js`:   
```javascript
import React from 'react';   
const person = (props) => {  
  return <div>{props.name}</div>;  
}  
export default person;
```  

**Smart component (internal state)**   
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

state: useful when need changes at runtime.  
E.g.: a card state such as "active" or "inactive". 

## What's a react component?  
A function that returns some JSX.
