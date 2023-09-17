# NODEJS

- NodeJS is built on Chrome's V8 engine. It comprises of memory heap and call stack. Whenever we declare a function or variable, memory is allocated to heap and whenever we call a function it is pushed to the call stack and popped from the call stack when the function returns. Call stack follows the LIFO (last in first out) principle.
- When running a setTimeout with 0 sec delay and an async IO method, the order of execution can never be guaranteed. (min time for setTimeout is 1ms so 0 will always be overridden)

### LIBUV

- LibUV is a cross platform library written in C language which handles all the async operations in NodeJS. It provides event loop and thread pool for handling async io in NodeJS.
- LibUV will try to utilize OS' async features and if they are not available then it will utilize it's threadpool.
- Modules like **fs**, **crypto**, **dns lookup**, and **zlib** are all synchronous so their operations are sent to LibUV's threadpool to prevent main thread (Event Loop) from blocking.

- #### EVENT LOOP

  - Event loop in NodeJS is a fundamental part of the main thread. The event loop is a crucial component of the main thread responsible for managing async operations, callbacks, and I/O operations without blocking the main thread.
  - When an asynchronous operation, such as a timer (e.g., setTimeout), I/O operation (e.g., reading a file), or network request, is encountered in the code, Node.js doesn't block the main thread. Instead, it delegates the execution of that asynchronous task to external system libraries or APIs.
  - The event loop, which is part of the main thread, continually checks the status of these asynchronous tasks. When a task is completed, its associated callback is placed in the appropriate queue (e.g., callback queue or microtask queue).
  - While the main thread is idle (i.e., there is no more synchronous code to execute), the event loop starts processing items in the callback queues, executing the associated callbacks one by one.
  - ##### CALL STACK PRIORITY
  - Syncronous code (only after the call stack is empty, then event loop will start executing async code)
  - Callbacks in microtasks queue (nextTick queue and then promise queue)
  - Callbacks in timer queue (SetTimeout and SetInterval)
  - Callbacks in microtasks queue (nextTick queue and then promise queue)
  - Callbacks in IO queue
  - Callbacks in microtasks queue (nextTick queue and then promise queue)
  - Callbacks in check queue (SetImmediate)
  - Callbacks in microtasks queue (nextTick queue and then promise queue)
  - Callbacks in close queue (Close handlers)
  - One final time microtasks queue (nextTick queu and then promise queue)

- #### THREAD POOL

  - Any functions that are sent to threadpool will run in a separate worker thread to prevent the main thread from blocking.
  - Once the task in the worker thread is completed, NodeJS uses a callback mechanism to notify the main thread (event loop).
  - No of threads spawned in the threadpool are defined via an environment variable **UV_THREADPOOL_SIZE**. By default the count is **4** and can be changed by assigning the variable a new value if the CPU running the NodeJS application has more cores.

### STREAMS AND BUFFERS

- Stream is a sequence of data that is being moved from one point to another. Useful for processing chunks of data instead of waiting for the complete data. Also useful in audio/video streaming.
- A buffer represents a chunk of memory allocated on our computer. Buffer objects are used to represent a fixed-length sequence of bytes. Many Node.js APIs support Buffers.
- In nodejs, buffers are used for store raw binary data. e.g data from a stream would be stored in a buffer before it gets processed.
- console logging a buffer in nodejs will print the hex version of the data:

```javascript
const buffer = Buffer.from("daniel");

console.log(buffer); // prints <Buffer 64 61 6e 69 65 6c>
console.log(buffer.toJSON()); // prints { type: 'Buffer', data: [ 100, 97, 110, 105, 101, 108 ] }
console.log(buffer.toString()); // prints "daniel"

//buffers are fixed length
buffer.write("daniel@gmail.com");

console.log(buffer.toString()); // prints "daniel"
```

- NOTE: check filesystem section for stream example

### CHARACTER SETS AND ENCODING

- Generally characters are represented by character codes e.g 86 is the numeric representation of character V.
- Character encoding dictates how to represent a number in a character set as binary data before it can be stored in a computer.
- UTF8 states that characters should be encoded in bytes (8 bits)

### CALLBACKS

- Functions are first class objects. They can be passed as parameters to a function and can also be returned from a function as a value.
- A function passed as a parameter to another function is called callback.
- A function that accepts another function as it's argument is called higher order function
- Synchronous callbacks are those callbacks that are executed immediately.
- Asyncronous callbacks are those callbacks that are executed after an async operation has completed (when an event has occurred).

```javascript
const obj = {
  name: "Daniel",
};

const obj2 = obj;

obj2.name = "John";

console.log(obj.name); // logs "John"
```

### MODULES

- Each module in nodejs has its own scope and the way nodejs achieves that is with IIFE pattern (immediately invoked function expression). so every module is wrapped in an IIFE: (with IIFE each function gets it own private scope)

```javascript
(function () {
  const heroName = "Superman";
  console.log(heroName);
})();
```

- Nodejs wraps every module with these params:

```javascript
(function (exports, require, module, __filename, __dirname) {
  const heroName = "Superman";
  console.log(heroName);
})();
```

- Nodejs caches the modules whenever we run the require statement so when the second time we require that module it will get that from the cache instead of re-requiring it.
- Just like objects, modules also behave the same so if we do just exports.prop instead of modules.exports = { prop } so the reference will break.
- To use ES modules, all javascript files need to have .esm extension.

### PATH MODULE

- Useful methods:
  - path.join (join just concatenates parts but may not return an absolute path)
  - path.resolve (resolve always returns an absolute path)
  - path.basename
  - path.extname
  - path.parse
  - path.format

### EVENTS MODULE

- **events** module allows use to work with events in nodejs.
- **events** module gives us **EventEmitter** class to work with events.
- We can have multiple listeners for the same event.

### FILESYSTEM

```javascript
const fs = require("fs");

//By default, it returned binary data so need to set encoding
const fileContents = fs.readFileSync("./test.txt", "utf-8");

//Asynchronously read file
fs.readFile("./test.txt", "utf-8", (err, data) => {
  if (err) {
    throw err;
  }

  console.log(data);
});

//Create file and write to it. (overrides if file exists)
fs.writeFileSync("./greeting.txt", "Hello World");

fs.writeFile("./greeting.txt", "Hello World", (err) => {
  if (err) {
    throw err;
  }
});

//Appends to existing file
fs.appendFile("./greeting.txt", "From Nodejs", (err) => {
  if (err) {
    throw err;
  }
});

//"a" flag on writeFile method will also append to file
fs.writeFile("./greeting.txt", "Hello World", { flag: "a" }, (err) => {
  if (err) {
    throw err;
  }
});

fs.mkdir("./test-dir", {}, (err) => {
  if (err) {
    throw err;
  }
});

//recursively create directories
fs.mkdir("./test-dir/another-dir", { recursive: true }, (err) => {
  if (err) {
    throw err;
  }
});

fs.rename("./greeting.txt", "./hello.txt", () => {
  if (err) {
    throw err;
  }
});

//Streams

const readableStream = fs.createReadStream("./file.txt", {
  encoding: "utf-8",
  highWaterMark: 2, //each chunk will be 2 bytes (default is 64)
});

const writeableStream = fs.createWriteStream("./file2.txt");

readableStream.on("data", (chunk) => {
  console.log(chunk);

  writeableStream.write(chunk);
});

//or we can just pipe the stream without needing to listen on "data" event
readableStream.pipe(writeableStream);
```
