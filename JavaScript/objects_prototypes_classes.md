# Objects, prototoypes and classes.

## Tips 
- Object literals {}
    - Property and values (key value pair)
    - You can add methods 
    - Has similarities with classes.
    - This keyword can be used in the object
    - Has shorthanded syntax.
    - === is best to use.
    - When comparing the following: it is actually comparing the memory adress instead of the values.
        - Strings compare values. 
    - Watchout for mutating the original object. 

```
 let person1 = {
    firstName: 'Jim',
    lastName: 'Cooper',
  };
  
let person2 = {
    firstName: 'Jim',
    lastName: 'Cooper',
  };

  person1 == person2 // false
  person1 === person2 // false
  object.is(person1, person2) // false

  let person2 = person1 then everything becomes true

```
- Object properties
    - Bracket notation is possible for objects with properties.
    - Each property has a descriptor. Object.getOwPropertyDescriptor()
        - Changing the property is also possible with defineProperty()
        - Writable -> only specifies the pointer. That cannot be changed. Childs of them can be changed. (property frozen freezes so this is not possible)
        - Enumerable -> setting it to false -> makes it not visible for .keys, json serialization. basicly it is not iteratble
        - Configurable -> locks down a property to prevent writable, enumerable to be changed.
    - Getter and setters both live on the prototype.
        - Getter is enumarable false
        - Getters and setters allow you to define Object Accessors (Computed Properties).
        - Better data quality
        - It gives simpler syntax
        - It allows equal syntax for properties and methods
        - It can secure better data quality
        - It is useful for doing things behind-the-scenes

- Prototypes
    - It is on every javascript function. 
    - Object prototype and function prototype are different. 
    - Function prototoype -> A functions prototype is the object instance that will become the prototype for all objectes created using this function as a constructor. function.prototype
    - Object prototype -> An object protottype is the object instance from which the object is inherited. object.__proto__
    - inheritance for the prototypes can be used with new. They point to the same memory prototype.
    - Instance vs prototypes
        - If age is specified: jim.age is 18 but jim.__proto__.age is still 29.
        - if not then it will use the prototypes ages
    - instance property overrides the prototype property.

- Classes
    - Syntactical sugar. 
    - it is basicly a constructor function. 
    - The properties can be manipulated with e.g. defineProperty.
    - Classes have prototypes as well. 
    - static properties and methods can be accesed before the initiation of the class.

- Built in objects in javascript: Math, Date, Regex.
## own opinion
Personally I love classes because it is cleaner. The background effects are basicly the same.