# Optimizing javascript bootup

## Intro
* Delivering less JavaScript can mean less time in network transmission, less spent decompressing code and less time parsing and compiling this javascript.
* JavaScript is more expensive for the browser to process than the equivalently sized image or web font.
	* JavaScriptBytes !== JPEGBytes
	* Images don't block the main thread or prevent interfaces. JS however can delay interactivity due to parse, compile and execution costs.
* Network capabilities and device capabilities don't always match up. 
	* A user with an amazing fiber connection doesn't necessarily have the best CPU to parse and evaluate.
	* A terrible network connections, but blazing fast CPU.
* JavaScript can impact page performance in other ways.
	* Memory, Pages can pause due to garbage collection.
	* Avoid memory leaks.
	* During runtime js can block the main thread causing pages that are unresponsiveness. (using requestAnimationFrame() or requestIdleCallback() for scheduling) can minimize responsiveness issues.
* 

## Progressive Bootstrapping
[Progressive Bootstrapping](https://twitter.com/aerotwist/status/729712502943174657)


## Network
* client -> server
* 1. order of type of elements requested. HTML, CSS, JS, Images.

### Code Splitting
* https://developers.google.com/web/updates/2017/06/supercharged-codesplit
* Lazily Loading.
* 

### Minification
* UglifyJS for minification.
* babel-minify or uglify-es to minify ES2015.

### Compression
* Use gzip to compress.
* Consider using [Brotli](https://www.smashingmagazine.com/2016/10/next-generation-server-compression-with-brotli/)

### Remove Unused code
* Identify opportunities for code that can be removed or lazily loaded.
* Use babel-preset-env and and browserlist to avoid transpiling features already in modern browsers.
* Tree shaking, Clousure compiler's optimizations. Webpack contextReplacementPlugin

### Caching
* http caching
* V8;s code cache
* filename hashing

## References
[1]. [Javascript Startup Optimization](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/javascript-startup-optimization/)

