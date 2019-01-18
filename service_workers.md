# Service Workers

## Intro
* Service worker is a script that runs in the background, separate from web page.
* Service worker opens door to features like 
	* push notifications, 
	* background sync, 
	* periodic sync, 
	* geofencing, 
	* intercept/handle network requests, 
	* programatically managing cache etc.
	* allows to support offline experiences.
* It is a javascript worker, so it cann't access DOM directly. Instead service worker communicate with the pages by responding to messages sent via "postMessage".
* Information taht need to persist and reuse across restart should make use of IndexedDB API.
* Service workers make extensive use of promises.
* Service workers can be deployed only with SSL connections(https).
* GITHUB pages are served over SSL for testing(localhost also works without issues.)


## Life Cycle of servrice Worker
* Register
	* registration of SW can be in javascript, it will cause the browser to start the service worker install step in the background.
* During Register/install step programmer will cache some static assets. If all files are cached successfully, then the service worker becomes installed. Otherwise service worker won't activate and retries to install it.
* Control
	* service worker will control all pages that fall under its scope, page that registered the service worker for the first time won't be controlled until it is loaded again.
* When service worker is in control, it will have two states.
	* service worker will be terminated to save memory or
	* It will handle fetch and message events that occur when network request or message is made from the page.
* 

## Registering A Service Worker
```
if ('serviceWorker' in navigator) {
    window.addEventListener('load', function() {
      navigator.serviceWorker.register('/sw.js').then(function(registration) {
        // Registration was successful
        console.log('ServiceWorker registration successful with scope: ', registration.scope);
      }, function(err) {
        // registration failed :(
        console.log('ServiceWorker registration failed: ', err);
      });
    });
  }
```

* enabled service workers can be seen at url chrome://inspect/#service-workers
* service worker details can be seen at url chrome://serviceworker-internals


## References
[1]. [Service Workers-- Google](https://developers.google.com/web/fundamentals/primers/service-workers/)
[2]. [The Basics of Web Workers](https://www.html5rocks.com/en/tutorials/workers/basics/)
[3]. [A beginner's guide to Service Workers](https://medium.com/samsung-internet-dev/a-beginners-guide-to-service-workers-f76abf1960f6)















