# Variable, types, this, spread

## Tips 
- Use let instead of the old var
    - Main difference is scoping. Let is scoped in the {} and var for the functions scope
    - Vars are hoisted which give undefined instead of reference errors
    - redeclaration of the same let keyword is not possible in the same scope
    - var creates a global property.
- Template literals are usefull when working with dynamic values that need to be inserted into strings.
- Destructing syntax for array can be done with multiple variables. Personally I dont like this feature. 
- String testing can be done with if statements, variables and string manipulation like lowercase, startwith endswith etc.
- Symbols (primitive data types) identifier for object properties
    - are rarely used. 

- Primitive types: String, Number, BigInt, boolean, symbol
- Primitive data types: boolean, null, undefined, number, string
- Object Data types: new array, new error, new function, new object, new regexp,
    - do not use new Boolean, new Number, new String. They cost more memory space and are slower to acces.
- Everything inherits from the object data types except the primitives
- use primetives as much as possible.

- Truthy and Falsy
    - In JavaScript, a truthy value is a value that is considered true when encountered in a Boolean context. All values are truthy unless they are defined as falsy (i.e., except for false, 0, -0, 0n, "", null, undefined, and NaN).

- This: Refers to an object, the object in which the code is running and the object can be changed.

- Spread operator:
    - Expand any iterable such as string or arry into array
    - For passing multiple arguments to method
    - The syntax uses ...
    - Always on the right-side of an equal sign.
    - Can add two arrays together. 
    - Can be used for parameters in functions.
- Copying objects is interesting because it can change the original object. 
    - Objects are copied by reference. 
    - So you need to deep copy them.
    - Shallow copy is possible with ... then it uses the values instead of reference.

## own opinion
Symbols are rarely used so I will dive deeper into them when it is necassary. It is good knowing the difference between var and let. The destructering of arrays into variable can be clunky in my opinion. I think it does not increase the readability.