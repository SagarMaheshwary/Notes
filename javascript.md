# JAVASCRIPT

### NOTES

- Handling promises concurrently
  - Promise.all() It takes an array of promises and returns a new promise that resolves only if all the input promises resolve successfully, or it rejects as soon as any of them rejects.
  - Promise.allSettled() It takes an array of promises and returns a new promise that resolves when all the input promises have settled (either resolved or rejected).
  - Promise.any() It takes an array of promises and returns a new promise that resolves as soon as any of the input promises resolve (successfully), or it rejects if all of them reject. It's designed to work with multiple promises but only needs one of them to succeed.
  - Promise.race() It takes an array of promises and returns a new promise that resolves or rejects as soon as the first promise in the input array settles (either resolves or rejects). It doesn't matter whether the first promise resolves or rejects; the result of that promise determines the outcome of the race.
- Function call, apply, and bind:

  - The **call** method is used to invoke a function with a specific **this** context and a list of arguments provided individually.
  - The **apply** method is similar to call, but it accepts arguments as an array or an array-like object.
  - The **bind** method is used to create a new function with a specified **this** value and optional arguments. It allows you to fix the context (**this** value) of a function and, if needed, provide some initial arguments that cannot be changed when the new function is invoked.

- Type of functions in javascript:

  - Named functions
  - Anonymous functions
  - IFFE functions (Immediately invoked function expression)
  - Async functions
  - Generator functions

### TOPICS

- Event Loop
- Queue
- Call Stack
- Hoisting
- Currying
- Callbacks
- Callback hell
- Promises
- Create a Promise
- Convert callback into Promise
- Async/Await
- setTimeout and setInterval
- Promise Priority
- Prototype inheritance and Prototype chaining
- Pure functions
- Closures
- Normal function vs arrow function scope
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
