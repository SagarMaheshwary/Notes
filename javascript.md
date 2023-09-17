# JavaScript

### FUNCTIONS

- In JavaScript, functions are first class objects. They can be passed as parameters to a function and can also be returned from a function as a value.
- A pure function is a function that always produces the same output for the same given input (arguments) and has no side effects.
- Type of functions in JavaScript:

  - Named functions
  - Anonymous functions
  - IFFE functions (Immediately invoked function expression)
  - Async functions
  - Generator functions
  - Constructor functions

- #### CALLBACKS

  - A function passed as a parameter to another function is called callback.
  - A function that accepts another function as it's argument is called higher order function
  - Synchronous callbacks are those callbacks that are executed immediately.
  - Asyncronous callbacks are those callbacks that are executed after an async operation has completed (when an event has occurred).
  - **Callback hell** in JavaScript refers to a situation where you have deeply nested callback functions, making the code difficult to read, maintain, and reason about. This typically occurs in asynchronous JavaScript code when dealing with multiple levels of callbacks, especially when performing I/O operations like reading files, making network requests, or working with databases.

- #### ARROW FUNCTIONS

  - Arrow functions have a shorted syntax than traditional functions but the most important point is that they don't have their own **this** context instead, they inherit **this** value from the outer function (lexical) context.
  - **Implicit Return**, If the function consists of a single expression, you can omit the braces **{}** and the **return** keyword. The result of the expression is automatically returned.

- #### CLOSURES

  - In JavaScript, a **closure** is a function that has access to variables from its outer (enclosing) function's lexical scope, even after the outer function has finished executing.
  - Lexical scoping means that functions are executed in the scope in which they are defined, not in the scope in which they are called. This property allows functions to "remember" variables and values from their outer scope.

- #### CALL, APPLY, BIND
  - In JavaScript, call, apply, and bind are methods available for functions, and they are used to manipulate how a function is invoked and to set its context (the value of this inside the function).
  - The **call** method is used to invoke a function with a specific **this** context and a list of arguments provided individually.
  - The **apply** method is similar to call, but it accepts arguments as an array or an array-like object.
  - The **bind** method is used to create a new function with a specified **this** value and optional arguments. It allows you to fix the context (**this** value) of a function and, if needed, provide some initial arguments that cannot be changed when the new function is invoked.

### PROMISES

- In JavaScript, a promise is an object representing the eventual completion or failure of an asynchronous operation. Promises are a fundamental part of handling asynchronous code, providing a more structured and elegant way to work with asynchronous tasks compared to traditional callback-based approaches.
- States of a Promise:
  - **Pending**, Initial state of a promise when it's created (neither failed nor resolved)
  - **Fulfilled (Resolved)**, When an async operation has been completed. In this state, promise holds the result value that the async operation has produced.
  - **Rejected**, A promise transitions to the rejected state when the asynchronous operation encounters an error or fails. In this state, promise holds the reason or error object that provides information about why the promise has failed.
- A promise is a part of microtask queue in the event loop mechanism and has higher priority of execution that macrotask queue (callbacks, timers, etc)
- Below are the methods to handle multiple promises concurrently
  - **Promise.all()** It takes an array of promises and returns a new promise that resolves only if all the input promises resolve successfully, or it rejects as soon as any of them rejects.
  - **Promise.allSettled()** It takes an array of promises and returns a new promise that resolves when all the input promises have settled (either resolved or rejected).
  - **Promise.any()** It takes an array of promises and returns a new promise that resolves as soon as any of the input promises resolve (successfully), or it rejects if all of them reject. It's designed to work with multiple promises but only needs one of them to succeed.
  - **Promise.race()** It takes an array of promises and returns a new promise that resolves or rejects as soon as the first promise in the input array settles (either resolves or rejects). It doesn't matter whether the first promise resolves or rejects; the result of that promise determines the outcome of the race.
- #### ASYNC/AWAIT
  - **async/await** is a feature in JavaScript that simplifies working with asynchronous code, making it more readable and easier to reason about.
  - An async function always returns a promise.
  - The await keyword pauses the execution of an async function until the promise is resolved. This makes asynchronous code look more like synchronous code and allows you to use the result of an asynchronous operation directly.
  - We can use traditional **try/catch** block for handling rejection case of a promise when awaiting an async function.

### PROTOTYPE

- Prototype in JavaScript is a mechanism for inheriting properties from one to object to another. By default JavaScript will try to find the called property on the object itself and if it does not find it then it will try to find it on object's prototype until the property is found or the prototype chain ends. (when a prototype in the object becomes null)
- Every object we create inherits from Object.prototype. (means every object has a built-in prototype property, though there are some ways to create objects without it)
- Overriding a property/method of a prototype is called property shadowing.
- **Object.create()** allows you to create an object with a specified object as it's prototype.
- **Object.getPrototypeOf(obj)** can be used to get the prototype of an object (there's also **obj.\_\_proto** property available)
- **Object.assign** can be used to merge objects and can also assign prototype to an object (newer versions of js can use spread operators)

### TOPICS

- Event Loop
- Queue
- Call Stack
- Hoisting
- Currying
- Create a Promise
- Convert callback into Promise
- setTimeout and setInterval
- What happens when you declare a method with function keyword and arrow function in a class.
- High Order functions
- var vs let vs const
- Value Types and Reference Types
- Primitive types
- forEach, map, reduce, filter
- Map and Set data structures
- Temporal dead zone (TDZ)
- **this** keyword
- Higher order functions vs first class functions
