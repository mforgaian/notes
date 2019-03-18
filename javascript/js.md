# Important Concepts and Use cases in javascript

## Async Functions
Async functions allow to write promise based code as if it were synchronous but without making main thread. Async functions makes code less clever more readable.

```
async function myFirstAsyncFunction(){
  try {
    const fulfilledValue = await promise;
  }
  catch (rejectedValue) {
    // …
  }
}
```
* if async keyword used before function definition, one can use use await within the function. When you await a promise the function is paused in a non-blocking way until the promise settles. If the promise fulfills we will get the value back otherwise rejected value is thrown.

## Async Return Values

Async functions always return a promise, whether you use await or not. That promise resolves with whatever the async returns, or rejects with whatever the async function throws.

```
//wait for ms milliseconds
function wait(ms){
  return new Promise(r => setTimeout(r, ms));  
}
```
```
async function hello(){
  await wait(500);
  return 'world';
}
```
calling hello returns a promise that fulfills with world.

```
async function foo(){
  await wait(500);
  throw Error('bar');
}
```
calling foo() returns a promise that rejects with Error('bar')

### Examples
Using Promises
```
function logFetch(url){
  return fetch(url)
    .then( response => response.text())
    .then( text => {
      console.log(text);
    }).catch(err => {
      console.error('fetch failed', err);
    })
}
```
Using Async
```
async function logFetch(url){
  try{
    const reponse = await fetch(url);
    console.log( await response.text);
  }catch(err){
    console.log('fetch failed', err);
  }
}
```
It is the same number of lines but all the callbacks are gone. This make it way easier to  read.
## Promises

## Service Workers

## How to modularize code
* Function Calling
```javascript
Trollbox = function(){};
Trollbox.prototype.foo = function(){
  alert('i can be called from other files too :');
}
```
* Function Definition
```javascript
var trollbox = new Trollbox();
trollbox.foo(); // ll show alert
```
## How to chain methods

* Defining Methods
```
function SimpleWidget(spec) {
    var instance = {}; // <-- A

    var headline, description; // <-- B

    instance.render = function () {
        var div = d3.select('body').append("div");

        div.append("h3").text(headline); // <-- C

        div.attr("class", "box")
           .attr("style", "color:" + spec.color) // <-- D
           .append("p")
               .text(description); // <-- E

        return instance; // <-- F
    };

    instance.headline = function (h) {
        if (!arguments.length) return headline; // <-- G
        headline = h;
        return instance; // <-- H
    };

    instance.description = function (d) {
        if (!arguments.length) return description;
        description = d;
        return instance;
    };

    return instance; // <-- I
}
```

* Chaining Methods
```javascript
var widget = SimpleWidget({color: "#6495ed"})
        .headline("Simple Widget")
        .description("This is a simple widget demonstrating functional javascript.");
widget.render();
```

## Comparing decimal fractions
While dealing with decimal input with that has fractional values upper bound error need to be taken into consideration. This upper bound is called as **machine epsilon**
```
0.1+0.2 === 0.3; // false
var epsEqu = function () { // IIFE, keeps EPSILON private
        var EPSILON = Math.pow(2, -53);
        return function epsEqu(x, y) {
            return Math.abs(x - y) < EPSILON;
        };
}();

epsEqu(0.1+0.2, 0.3); //true
```

## Quota Management
https://dvcs.w3.org/hg/quota/raw-file/tip/Overview.html#idl-def-StorageQuota

## Font Load Events
http://dev.w3.org/csswg/css-font-loading/#font-face-set-ready

## Service Worker
https://github.com/slightlyoff/ServiceWorker/blob/cf459d473ae09f6994e8539113d277cbd2bce939/service_worker.ts#L17

## Web MIDI
https://webaudio.github.io/web-midi-api/#widl-Navigator-requestMIDIAccess-Promise-MIDIOptions-options

## Streams
https://github.com/whatwg/streams#basereadablestream


## Reference
[1].[Async Functions](https://developers.google.com/web/fundamentals/primers/async-functions)
[2].[Promises](https://developers.google.com/web/fundamentals/primers/promises)
[3].[Service Workers](https://developers.google.com/web/fundamentals/primers/service-workers/) 
