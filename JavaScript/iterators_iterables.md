# Iterators and iterables

## Tips 
- An iterator lets you iterate through a collection's contents one at a time, pausing at each item.
- an iterator is any object that implements the iterator protocol by having a next() method that returns a value property and a done property
- An iterable: An array is a built in iterable
    - There are other built-in iterables, strings maps and sets
    - iterables implement the @@ iterator method.
    - Symbol.iterator a well known symbol in javascript
- Iterator Interface
    - Property Next
    - property: throw
    - Property:return
- Iterator result interface
    - Property: done
    - Property: value

- Generator Functions
    - Definition: A function that can be paused and resumed at a later time, while having the ability to pass values to and from the fucntion at each pause point.
    - Syntax function* gen(){ }
        - Must include a astrix *
    - Executing the generator function alone does not execute its containing code.
    - To start an iterator you need to use next() on the function call.
- Yield keyword signals the pause point of a generator function.
    - Send a value to the iterator,
    - receive a value from the iterator
    - Yield experession can be used like normal expressions.
- Yield delegation
    - Definition: Yield delegation essentially allows a host generator function to control the iteration of a different generator function.
- Error handling
    - Generator funcitons include Return and throw.
- 


## own opinion
I already used a lot of iterators. The generator functions is something that is interesting but I am not sure how the readability will be when you add multiple yields. WHy not create multiple functions? 