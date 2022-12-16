# node-intro

### A bit of history
- Ruby and rails era dhh (beautiful syntax, basecamp)
	- Progress bar on flickr - mongrel web server:
		1. iFrame to update progress bar
		2. Ajax requests
		3. Long polling.
- Wrote server in C + ruby but each line of ruby got 5% slower.
- Wrote web server in C -> avg web developer could not use it.
- python, lua, haskl, with non blocking system. Problem was libs.
- V8 was released in 2008, small communities of JS (Netscape).
- Make servers fast and less painfully to set up.
- Joyent -> data centers hosting node.


### Why asynchronous and synchronous I/O?
- History of frameworks of concurrency and threads.
- Original Node.js presentation-> https://www.youtube.com/watch?v=ztspvPYybIY

### Why JavaScript 
- The only lib without sync modules

### Where did Node.js come from?
- Server framework for using async code
- V8 chrome engine
- Asynchronous event-driven JavaScript runtime

### What is a callback.
- A way to implement async IO in abstract

```js
function greet(name, callback) {
    console.log('Hi' + ' ' + name);
    callback();
}

function callMe() {
    console.log('I am callback function');
}

greet('Peter', callMe);

// What is a promise and why (callback hell)?
// A Promise is an object representing the eventual completion or failure of an asynchronous operation.
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("foo");
    console.log("foo");
  }, 3000);
});
```

### .then() vs. async+await

```js
function one() {
  return new Promise(resolve => {
    console.log("one");
    resolve();
  });
}

function two() {
  return new Promise(resolve => {
    console.log("two");
    resolve();
  });
}

function three(){
   console.log("three")
}

// .then
one().then(() => two()).then(() => three());

// async await
await one();
await two();
await three();
```
 
### Non-blocking vs. blocking I/O
