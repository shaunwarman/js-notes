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

