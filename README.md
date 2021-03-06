# js-notes
--------

##### Closure - [Examples] (https://gist.github.com/shaunwarman/87d701f64cae8adff3e8.js)
A closure is an inner function that has access to the variables in the outer (enclosing) function’s scope chain. The closure has access to variables in three scopes; specifically: 
- (1) variable in its own scope 
- (2) variables in the enclosing function’s scope 
- (3) global variables.

##### Hoisting - [Examples] (https://gist.github.com/shaunwarman/c5573bb6b952c317e176)
Because variable declarations (and declarations in general) are processed before any code is executed, declaring a variable anywhere in the code is equivalent to declaring it at the top. This also means that a variable can appear to be used before it's declared. This behavior is called "hoisting", as it appears that the variable declaration is moved to the top of the function or global code.

For that reason, it is recommended to always declare variables at the top of their scope (the top of global code and the top of function code) so it's clear which variables are function scoped (local) and which are resolved on the scope chain.

##### Strict mode
- First, strict mode eliminates some JavaScript silent errors by changing them to throw errors. 
- Second, strict mode fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode. 
- Third, strict mode prohibits some syntax likely to be defined in future versions of ECMAScript.
```
// top of js file or function
'strict mode';
...
```
Strict mode changes both syntax and runtime behavior. Changes generally fall into these categories: 
- changes converting mistakes into errors (as syntax errors or at runtime)
- changes simplifying how the particular variable for a given use of a name is computed
- changes simplifying eval and arguments
- changes making it easier to write "secure" JavaScript 
- changes anticipating future ECMAScript evolution.

##### Pass by.. [Examples] (https://gist.github.com/shaunwarman/ff9a05348684a005b087)
Javascript is pass by value.. unless that value is a reference to an object.

##### Prototype [Examples] (https://gist.github.com/shaunwarman/7c34985e81a28688d4f4)
When it comes to inheritance, JavaScript only has one construct: objects. Each object has an internal link to another object called its prototype. That prototype object has a prototype of its own, and so on until an object is reached with null as its prototype. null, by definition, has no prototype, and acts as the final link in this prototype chain.

[[Prototype]] is looked at recursively, i.e. a1.doSomething, Object.getPrototypeOf(a1).doSomething, Object.getPrototypeOf(Object.getPrototypeOf(a1)).doSomething etc., until it's found or Object.getPrototypeOf returns null.

###### Inheriting properties
JavaScript objects are dynamic "bags" of properties (referred to as own properties). JavaScript objects have a link to a prototype object. When trying to access a property of an object, the property will not only be sought on the object but on the prototype of the object, the prototype of the prototype, and so on until either a property with a matching name is found or the end of the prototype chain is reached.
