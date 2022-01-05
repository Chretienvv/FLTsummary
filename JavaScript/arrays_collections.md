# Arrays and collections

## Tips 
- Possible ways of creating arrays
    - Array.of(1,2,3) (new array performs slower)
    - let example = []
    - spread operator for other variables or functions.
- lots of array methods inside javascript like find, includes, fill, foreach etc.
- Data collections in es6 
    - Data collection stores and structures large amounts of data for easy acces.
    - Sets, maps, weaksets and weakmaps.
- Data Types: Boolean, null, undefined, number, bigint, string, symbol, objects. Only objects is not primitive.
- Sets
    - Enables you to store unique values of any type. 
    - NO duplicates
    - Properties 
        - set.size
    - Methods
        - add, clear, delete, entries, foreach, has, keys, values. 
- Difference between set and weakset
    - Weakset
        - Only contain objects
        - No primitive datayptes
        - Objects are held "weakly"
        - Not iteratable
        - No access to size property
        - garbage collected: Monitory memory allocation and determine when a block of allocated memory is no longer needed and reclaim it. 
    - Add delete has are the only methods.

- Maps
    - Definition: Map uses key value pairs and keeps the original insertion order of the keys. Any value objects and primitive values may be used as either a key or a value.
    - Different keys: strings, numbers. functions, objects.
    - Iterates in order unlike arrays
    - Properties and methods
        - size - clear, delete, entries, foreach, get, set, has, keys, values.
    - Difference between Maps and objects
        - Faster searching in maps
        - Element order
        - Inheritance Map is inherited from a object. 
- Weak map
    - Keys must be objects
    - Objects are held weakly
    - not iteratable
    - garbage collected
    - weakmaps are not enumerable
    - Delete get set has

- Typed Arrays
    - Definition: Arraylike objects that provide a mechansim for accessing raw binary data
    - Benefits
        - Raw binary data
        - Faster performance
        - strictly controlled data
        - APIs that support typed arrays.
    - Array buffer
        - JS file cant communicatie to the array buffer.
- standard vs typed
    - accept most data types vs restricted data typs
    - standard variable storage vs binary data
    - standard processing vs faster processing
    - .. vs once in view acts like array
    - .. vs native apis

## own opinion
The use of maps and sets are very specific in my opinion. They deliver value at scale but are not commonly used. 