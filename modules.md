**ES6 modules: what's the import/export syntax for default?**  
file `X.js`:   
`export default X;` // whenever import is called on that file, the export will be X.  
file `Y.js`:   
`import a from './path/to/X'` // a is the name given in Y for the default export of X. i.e., a will be X. Generally, to make it simpler/more readable:  
`import X from './path/to/X'` 

Beware:  
`import { X } from './path/to/X';` // This will break since this {} syntax is for **named** exports.   


**CommomJS modules vs ES6 modules: syntax diff?**   
CommomJS (node): `module.exports` , `require` 
ES6: `import x from '...'`, `import {x} from '...'`, `export`, `export default`
