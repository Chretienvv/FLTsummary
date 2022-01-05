# General Javascript concepts

## Tips & learnings
- Hoisting
    - e.g. var vs let. Var will return undefined if it is not intialized. Let will give a reference error

``` //The code we wrote
console.log(x);
var x = 100;

// How JavaScript interpreted it
var x;
console.log(x);
x = 100;
```
- Event Bubbling
    - Definition: When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors
    - Nice website with information: https://javascript.info/bubbling-and-capturing 

Perfect example of how the bubble effect works.
```
<body onclick="alert(`the bubbling doesn't reach here`)">
  <button onclick="event.stopPropagation()">Click me</button>
</body>

```
- DOM Manipulation
    - Grab the html element with e.g. getElementById
- Scope
    - Function scope, block scope, variable scope
- Prototype

- Shadow Dom
    - Shadow host: The regular DOM node that the shadow DOM is attached to.
    - Shadow tree: The DOM tree inside the shadow DOM.
    - Shadow boundary: the place where the shadow DOM ends, and the regular DOM begins.
    - Shadow root: The root node of the shadow tree.
    - Very usefull for encapsulation. 

- Strict
    - use strict is ignored by older browsers. 
    - Forces all variables to be declared.
    - Cant use reserved words as variables, cant delete variables and functions.
    - Best practice always use strict.

- Callbacks
    - Definition: A callback is a function passed as an argument to another function
    - Where callbacks really shine are in asynchronous functions, where one function has to wait for another function (like waiting for a file to load).
        - then, async, await

- Immediately Invoked Function Expression (IIFE)
    - The function executes itself immediately. Usefull in the need of scoping and when vars are used. For instance in for loops.  es6 fixes this with let.

- Arrow Functions
    - Definition: An arrow function expression is a compact alternative to a traditional function expression, but is limited and can't be used in all situations.
    - param => expression
Small example:
```
// Traditional Anonymous Function (no arguments)
let a = 4;
let b = 2;
function (){
  return a + b + 100;
}

// Arrow Function (no arguments)
let a = 4;
let b = 2;
() => a + b + 100;

```
- Classes

- Modules

- Default Parameters

- Rest and Spread Parameters
    - Rest
    - Spread

- Template Literals (string literals)
- Async & Await (ES2016+)

- Multi-line Strings
    - Difference in es5 and es6
    - es6 use the template literal. 
    - es5 "adsfsadf / dafsadf" 

- Destructuring
    - Spread operator, assigning mutliple variables from one array.

- Enhanced Object Literals

- Promises

- Block-Scoped Constructs: Let and Const
    - const is a signal that the identifier won’t be reassigned.
    - let is a signal that the variable may be reassigned, such as a counter in a loop, or a value swap in an algorithm. It also signals that the variable will be used only in the block it’s defined in, which is not always the entire containing function.

- For Of Comprehensions
    - For in/of loops with statements included
- Short circuiting
    - optimization for logical expressions. Bypass subsequent expressions in && or || based on truthy or falsy
    - If the first expressions false the rest will not be checked exp1 && exp2 same with or but then based on true
- Order of Precendence -> classic + is the latest and () is executed first.



## own opinion