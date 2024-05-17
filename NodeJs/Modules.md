Modules are like WebApi's provide by browser runtimes.

eg => we can use file handling like reading, writing, copying, etc on a file using js code, but js doesn't
have this functionality on it's own originally. this is provide by the nodeJs. just like webapi's like setTimeout() provided by the browser runtime.

to use the modules  we use **require()** syntax. it's same as using **import __ from __** in frontend libraries.

In node.js each file is a module but is isolated by default.

#### CommonJs - 
A question arises that let's say they are two files rn, one is index.js and one is app.js, how do we ask node.js to execute not just index.js but also app.js?
this is where commonJs standard comes into picture.
1. commonJs is a standard that states how a module should be structured and shared.

There are many types of modules - 
1. Local Modules.