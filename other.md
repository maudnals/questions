### Where exactly is the `React` variable used in a React component?   
JSX (return value of render() method) compiles to `React.createElement(...)`.   

### What are two ways of creating a react component?  
Dumb component (no state):
`Person.js`:  
`import React from 'react';  
const person = (props) => {
  return <div>{props.name}</div>;
}  
export default person;`

### What's the convention for a JSX file xtension?  
.jsx

### props vs state?  
props = a configuration (as a JS object, e.g. `{className: "app"}`).  
Stays the same at runtime.
