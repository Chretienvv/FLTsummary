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
    - It is on every javascript function. 
    - Object prototype and function prototype are different. 
    - Function prototoype -> A functions prototype is the object instance that will become the prototype for all objectes created using this function as a constructor. function.prototype
    - Object prototype -> An object protottype is the object instance from which the object is inherited. object.__proto__
    - inheritance for the prototypes can be used with new. They point to the same memory prototype.
    - Instance vs prototypes
        - If age is specified: jim.age is 18 but jim.__proto__.age is still 29.
        - if not then it will use the prototypes ages
    - instance property overrides the prototype property.

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
    - Syntactical sugar. 
    - it is basicly a constructor function. 
    - The properties can be manipulated with e.g. defineProperty.
    - Classes have prototypes as well. 
    - static properties and methods can be accesed before the initiation of the class.

- Modules
    - Importing and exporting file, classes, functions ,variables etc.

- Default Parameters

- Rest and Spread Parameters
    - Rest function(...arguments) infinte parameters
    - Spread can be used for destructering arrays or merging objects.

- Template Literals (string literals)
- Async & Await (ES2016+)
    - Syntactic sugar
    - Looks like synchronous but it is asynchronous
    - Async: designate that a function is asynchronous
    - Await: Must be used inside of async, only blocks current function. 
    - Same goal as promises
    - Return value is wrapped in a promise
    - Handling error with async await
        - Try, catch block for error handling. 
    - Chaining Async/await can be done with await on the variable of the original async await
        - const {data: originalcall} = await 
    - How can I make non-sequential calls?
        -  Not placing awaits on the original calls
        - In a later place you can wait with const {data:orginalcall } = await
    - Awaiting in parallel calls
        - Parallel calls is one of the powers in async programming.
        - Code example:
    - Multi-line Strings
        - Difference in es5 and es6
        - es6 use the template literal. 
        - es5 "adsfsadf / dafsadf" 

- Destructuring
    - Spread operator, assigning mutliple variables from one array.

- Enhanced Object Literals
     - Definition: Object literal enhancement is used to group variables from the global scope and form them into javascript objects. It is the process of restructuring or putting back together.
     - Multiple examples can be found here: https://www.geeksforgeeks.org/javascriptes6-object-literal-enhancement/ 
    
- Promises
    - Promise states:
    - Pending
    - Fulfilled
    - Rejected
    - Other terms -> setteld -> resolved. The promise is no longer pending. 

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
All of these concepts are important when you are developing in JavaScript. Some concepts are more common than others. In general it is good to keep this "cheat sheet" close when developing. 
