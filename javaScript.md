hoisting in let var const
Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that you can use a variable or function before its declaration in the code.

However, the way hoisting works differs between var, let, and const.

var Hoisting
Variables declared with var are hoisted to the top of their function or global scope and are initialized with undefined. You can access them before their declaration, but their value will be undefined.

```javascript
{
console.log(x); // Output: undefined
var x = 5;
console.log(x); // Output: 5
}

## let and const Hoisting
Variables declared with let and const are also hoisted to the top of their block scope. However, they are not initialized during hoisting. Accessing these variables before their declaration results in a ReferenceError. This period between entering the scope and the variable declaration is known as the Temporal Dead Zone (TDZ).



console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;      
console.log(y); // Output: 10
javascript
console.log(z); // ReferenceError: Cannot access 'z' before initialization
const z = 15;
console.log(z); // Output: 15

# In summary:

var: Hoisted and initialized with undefined, accessible before declaration.

let and const: Hoisted but not initialized, accessing them before declaration results in a ReferenceError due to the Temporal Dead Zone.

This behavior ensures safer and more predictable code, especially with let and const, by preventing the use of variables before they are properly declared and initialized. 

