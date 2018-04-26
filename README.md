# questions


## HTML

**What's the diff between querySelector and getElementById?**  
querySelector is faster

## CSS
 
**CSS class: .x .y vs x.y**  
**CSS class: not**  
**How to programmatically change a class in JS?"**  
**How would you implement style changes for a 4k screen (vs dev mode)?**  
`// Developer mode
@media screen and (min-width: 1367px) and (max-width: 3839px) {
   html {
     font-size: 8px;
   }
}
// Large 4K screen
@media screen and (min-width: 3840px) {
   html {
     font-size: 16px;
   }
}`

**How would you implement style changes for a 4k screen (vs dev mode)**" 


## JS: core

**Async with babel**

## Build process  

**Where does "env" come from?**

**Webpack: what's the difference between devServer and server?**

**Webpack: should you install webpack locally or globally?**  
Install Globally (`npm install -g webpack`):
When installed globally, webpack can be run using webpack command from the Command prompt/Terminal window.  
Install locally in the project folder (`npm install webpack --save-dev`):
When installed locally, you need to run webpack via npm script, but it's better for dependency management.

**Webpack: What is needed to require an HTML file as follows in index.js: `require('./index.html');`?**  
An HTML loader (in webpack.config.js)

## Real-time

**Message broker: what's the diff between a topic and queue, and when would you use one over the other?**  

## Data structures

**Is that a tree?**  
**Traverse a tree**  
**Write a state machine**

## Frameworks 

**React: you shouldn't mount on body tag, why?**

## Node

**What is node?**

**How to start a simple http server with node?**
`node http-server` (in the correct directory)

## Opinions  

**Why didn’t polymer get love from the community?**

