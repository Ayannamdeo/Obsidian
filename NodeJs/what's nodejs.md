Javascript is a unique language among others. When we talk about other languages
lets say python we are referring to the language itself and the runtime of that language, every 
language comes with it's runtime, its not like that python has its language and it's interpreter 
separated, it's all bundled up together.
But in case of Javascript this runtime and the language itself is separate.

The first implementation of javascript only allowed it to be executed in browsers, because only 
browsers  had this thing  called JS engine which the browsers used to execute the js code.

so executing js outside browsers wasn't possible until the developer of nodeJs Ryan Dahl 
took this js engine (V8 from chrome) and embedded the code with c++ and also added/removed 
few changes of his own to make   NodeJs runtime environment.

now js can be executed outside the browser and due to using c++ underhood we can use
js to talk to machine itself and do some stuff like file handling etc. which wasn't possible 
in browsers.

This file handling functionality can be accessed from node [[Modules]].

[[How NodeJs Works?]]

