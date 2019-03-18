# Promises

## Intro
* Javascript is single threaded. 

* At their most basic, promises are a bit like event listeners except:
	* A promise can only succeed or fail once. It can not succeed or fail twice, neither can it switch from success to failure or vice versa.
	* If a promise has succeeded or failed and you later add a success/failure callback, the correct callback will be called, even though the event  took place earlier.
## Promise Terminology
* fulfilled
* rejected
* pending
* settled


e.g.,
```
var promise = new Promise(function(resolve, reject){

  if(everything_is_fine){
    resolve("worked");
  }else{
    reject(Error('It broke'));
  }
})
```
how to use promise
```
promise.then(function(result){
  console.log(result);
}, function(err){
  console.log(err)
});
```

## catch
The difference is subtle, but extremely useful. Promise rejections skip forward to the next then() with a rejection callback (or catch(), since it's equivalent). With then(func1, func2), func1 or func2 will be called, never both. But with then(func1).catch(func2), both will be called if func1 rejects, as they're separate steps in the chain. Take the following:

```
asyncThing1().then(function() {
  return asyncThing2();
}).then(function() {
  return asyncThing3();
}).catch(function(err) {
  return asyncRecovery1();
}).then(function() {
  return asyncThing4();
}, function(err) {
  return asyncRecovery2();
}).catch(function(err) {
  console.log("Don't worry about it");
}).then(function() {
  console.log("All done!");
})
```

## Parallelism and Sequencing: Getting the best of both


## References
[1]. [Promises](https://developers.google.com/web/fundamentals/primers/promises)
