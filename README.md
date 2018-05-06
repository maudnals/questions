# questions


## HTML

**What's the diff between querySelector and getElementById?**  
querySelector is faster 

## Browsers
 
**What's teh main difference between Safari and Chrome?**  
Rendering engine
WebKit vs others => not the same tech support (e.g.
Also some minor differences in implementations (stroke-dash direction) 
Also in general Safari is more buggy (scroll behaviour: fixes needed, flexbox, etc.) 
Also political because they are tied to fifferent vendors (service workers in Safari) 

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

**How would you implement a theming system with css variables?** 

**Should one always use sass?**  
My favorite combination: sass for syntax capabilities (write less code) + css variables (instead of sass variables) for runtime variables. However, this depends on browser support (IE doesn't support CSS variables)

## JS: core

**Async with babel**  

## Modules 

**ES6 modules: what's the syntax?**  
myModule.js --- `export default hi;`   
index.js --- `import hello from './myModule';` (can use `hello` or whatever I like because export is default)


## Build process  

**Where does "env" come from?**

**Webpack: what's the difference between devServer and server?**

**Webpack: what is webpack-merge for?**   
It's useful to merge webpack configurations (common+dev or common+prod).  
Under the hood it's a bit like `object.assign`, but with a lot of webpack-specific functionality (regarding the order, for example).  

 
**Webpack: what is the HtmlWebpackPlugin for?**   
It creates a boilerplate HTML file that includes the bundles that webpack built.

**Webpack: should you install webpack locally or globally?**  
Install Globally (`npm install -g webpack`):
When installed globally, webpack can be run using webpack command from the Command prompt/Terminal window.  
Install locally in the project folder (`npm install webpack --save-dev`):
When installed locally, you need to run webpack via npm script, but it's better for dependency management.

**Webpack: What is needed to require an HTML file as follows in index.js: `require('./index.html');`?**  
An HTML loader (in webpack.config.js)  


**Wepack: what's the benefot of wrapping the config object as the return value of a function, instead of returning it directly?**  
e.g.:  
`module.exports = function(env) {
  return commonConfig;
}`  
Thanks to the function we can pass in arguments, such as the environment, and use them to build an appropriate config object that we then return.  


**Webpack: which module system should webpack configs use?**    

CommonJS (because node!)
=> `module.exports` , `require`
 
 
**Webpack: what do the following do?**     
path.join(__dirname, 'dist') --> returns the correct file path of currentDirectory/dist. 
path.resolve(__dirname, "../") --> returns the correct file path of parentDirectory/dist.
 
**Yarn vs npm: what's the difference?** 
Yarn was developed by Facebook in attempt to resolve some of npm’s shortcomings. Yarn isn’t technically a replacement for npm since it relies on modules from the npm registry. Think of Yarn as a new installer that still relies upon the same npm structure, and makes the same packages available. Yarn introduced a yarn.lock feature for deterministic dependency installs (just like with an npm shrinkwrap file, but in npm this wasn't automatic and required maintenance). Then with the release of npm 5, package-lock.json was added also to npm. 
Also: yarn sends package usage information to Facebook. Yarn was much faster than npm untill npm 5 eleased in '17 (and st ill a little faster after that).

**Yarn vs npm: how to add a package?**
`yarn add` vs `npm install`

**Should I put yarn.lock in .gitignore, or should I push it to the shared repo?**
Push it. That's the whole point. When you run either yarn or yarn add <package>, Yarn will generate a yarn.lock file within the root directory of your package. You don’t need to read or understand this file - just check it into source control. When other people start using Yarn instead of npm, the yarn.lock file will ensure that they get precisely the same dependencies as you have.


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

