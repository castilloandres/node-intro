# node-intro

1. A bit of history
  //ruby and rails era dhh
    // progress bar on flickr - mongrel web server
      // iframe to update progress bar
      // ajax requests
      // long polling
  //Wrote server in C + ruby but each line of ruby got 5% slower
  // Wrote web server in C -> avg web developer could not use it
  // python, lua, haskl, with non blocking system. Problem was libs.
  // V8 was released in 2008, small communities of JS (Netscape)
  // Make servers fast and less painfully to set up
  // joyent -> data centers hosting node
2. Why asynchronous and synchronous I/O? Original Node.js presentation-> https://www.youtube.com/watch?v=ztspvPYybIY
	// history of frameworks of concurrency and threads

3.Why JavaScript 
  // the only lib without sync modules
4. Where did Node.js come from?
	// server framework for using async code
  // V8 chrome engine
  // asynchronous event-driven JavaScript runtime
5. What is a callback.
// A way to implement async IO in abstract




// What is a callback.
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


// .then() vs. async+await

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

  one().then(() => two()).then(() => three());

await one();
await two();
await three();

 
 //non-blocking vs. blocking I/O
