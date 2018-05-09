## What is webpack's url-loader for?  
Webpack plugin url-loader will convert any asset url (either a path required from JS, or an asset URL in css) into a base-64 string inlined into my bundle. 
It's very nice for small assets, for which it's more performant to have it inlined in the bundle rather than making a new network request just for this.
