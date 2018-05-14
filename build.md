  
## Build process: general   

**Where does "env" come from?**

**Yarn vs npm: what's the difference?** 
Yarn was developed by Facebook in attempt to resolve some of npm’s shortcomings. Yarn isn’t technically a replacement for npm since it relies on modules from the npm registry. Think of Yarn as a new installer that still relies upon the same npm structure, and makes the same packages available. Yarn introduced a yarn.lock feature for deterministic dependency installs (just like with an npm shrinkwrap file, but in npm this wasn't automatic and required maintenance). Then with the release of npm 5, package-lock.json was added also to npm. 
Also: yarn sends package usage information to Facebook. Yarn was much faster than npm untill npm 5 eleased in '17 (and st ill a little faster after that).

**Yarn vs npm: how to add a package?**
`yarn add` vs `npm install`

**Should I put yarn.lock in .gitignore, or should I push it to the shared repo?**
Push it. That's the whole point. When you run either yarn or yarn add <package>, Yarn will generate a yarn.lock file within the root directory of your package. You don’t need to read or understand this file - just check it into source control. When other people start using Yarn instead of npm, the yarn.lock file will ensure that they get precisely the same dependencies as you have.


## Webpack 

  
**What is webpack's url-loader for?**  
Webpack plugin url-loader will convert any asset url (either a path required from JS, or an asset URL in css) into a base-64 string inlined into my bundle. 
It's very nice for small assets, for which it's more performant to have it inlined in the bundle rather than making a new network request just for this.  

**What's the difference between devServer and server?**   

**What is webpack-dev-server, how does it work, and why is it useful?** 
When developing an SPA, a dev server is useful, in order to serve static content.  
webpack-dev-server is a node module that is webpack's dev server.  
It uses express behind the scenes - it automatically emits bundles in memory and fire web socket requests to the web server so that the app updates automatically in the browser.  
A great popular feature is hot module reloading (browser refreshes automatically when changes are made), but also on top of that it enables for a rich dev environment/tooling.

**What is webpack-merge for?**   
It's useful to merge webpack configurations (common+dev or common+prod).  
Under the hood it's a bit like `object.assign`, but with a lot of webpack-specific functionality (regarding the order, for example).  

**What is the HtmlWebpackPlugin for?**   
It creates a boilerplate HTML file that includes the bundles that webpack builds. Especially useful when leveraging long-term vendor hashing (e.g. bundle name is hashed using the chunkhash template helper), so we don't need to update manually the bundle name in index.html

**Should you install webpack locally or globally?**  
Install Globally (`npm install -g webpack`):
When installed globally, webpack can be run using webpack command from the Command prompt/Terminal window.  
Install locally in the project folder (`npm install webpack --save-dev`):
When installed locally, you need to run webpack via npm script, but it's better for dependency management.

**What is needed to require an HTML file as follows in index.js: `require('./index.html');`?**  
An HTML loader (in webpack.config.js)  


**What's the benefot of wrapping the config object as the return value of a function, instead of returning it directly?**  
e.g.:  
`module.exports = function(env) {
  return commonConfig;
}`  
Thanks to the function we can pass in arguments, such as the environment, and use them to build an appropriate config object that we then return.  


**Which module system should webpack configs use?**    

CommonJS (because node!)
=> `module.exports` , `require`
 
 
**What do the following do?**     
path.join(__dirname, 'dist') --> returns the correct file path of currentDirectory/dist. 
path.resolve(__dirname, "../") --> returns the correct file path of parentDirectory/dist.  

**What does `module` mean in `webpack.config.js`?**  
Not very intuitive: `module` is an object in which is defined how webpack should deal with different types of modules. In the webpack sense, a module can be: an ES2015 import, an AMD require, a CommonJS require(), a CSS/SaSS/less @import, an image url in a stylesheet (url(...)) or html (<img src=...>) file.  

**How does a typical folder structure look like for webpack config?**  
`webpack.config.js`  (using webpackMerge)  

`build-utils/`   
|  
--- `webpack.common.js`  
--- `webpack.dev.js`  
--- `webpack.prod.js`  
--- `common-paths.js`
 

