### Where exactly is the `React` variable used in a React component?   
JSX (return value of render() method) compiles to `React.createElement(...)`.   

### What's JSX?  
JS that looks like HTML. Complied onto JS via Babel.

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
