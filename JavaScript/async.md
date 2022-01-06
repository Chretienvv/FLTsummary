# Async

## Tips 
- Common problem with fetching data
    - Which data comes first? This can create problems
- Callback pyramid (bad)
    - Other calls are buried in the original call. 
    - Bad for readability, functions do one thing
    - Callback pyramid of doom: A common problem that arises when a program uses many levels of nested indentation to control acces to a function.
    - Dirty code and handling errors. To many levels of abstraction
- Solving the callback pyramid -> promises
    - Object that represents the eventual completion or failure of an asynchronous operation, and its resulting value.
- Promise states:
    - Pending
    - Fulfilled
    - Rejected
    - Other terms -> setteld -> resolved. The promise is no longer pending. 
- Setting up meetings: https://github.com/taylonr/async-programming-promises 
- Handling errros can be done with error functions with .then( result => { }) and .catch
- Chaining promises -> watchout for the callback pyramid. 
    - return the promise and the thens
- Catching errors in a chain
    - with catch  and throw errors return that error so that the then errors are not chained. 
- Loading indicators are important to implement. 

- Aspects to consider when using promises
    - The promise states
    - Promise object new Promise()
    - Promise takes only one function the executed funtion
        - Like this: 
```
function timeout(){
    const wait = new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve("timeout!");
        }, 1500)
    });
    wait.then(text => setText(text))
}

```

- If the associated promise has already been resolved, either to a value, a rejection, or another promise, this method resole does nothing. 
- Rejecting a promise
    - With reject you can catch the reject after the .then
    - You can check on statuscodes with if statements and call the appropiate resolve or reject then.
- Waiting with a promise on other promises. 
    - .allsetteld
    - Catch blocks are recommended 
    - You can specify on what promises you need to wait.
- Racing promises
    - Using the closest endpoint. This enhances performance
    - Usage with promise.race
- Ways to Queue promises
    - All -> all or one fails
    - Allsetteld - > all out of pending state
    - Race -> until the fastests is fullfilled.

*** Async Await ***
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

```
async function parallel(){
    await Promise.all([
        (async ()=> {
            const {data} = await http.get("http://asdfasdf")
        })(),
        (async ()=> {
            const {data} = await http.get("http://asdfasdf")
        })()
    ])
}

```

## own opinion
No idea why tutorials use libraries....
Promises are the basics and old way. Async await is very usefull but I think it is important to correctly error handle the different responses. 
Playing with Api's is fun and the choice between parallel and concurrent is interesting. 
