# Service Workers

## Registering a service worker

To register a service worker we will need to use the navigator.serviceWorker method register and give it a path like so:

``` javascript
navigator.serviceWorker.register('sw.js');
```

This will register the servie worker with the browser and returns a promise, you will then get callbacks for success and failure.

You can also pass a scope as the second parameter of the register call like so:

``` javascript 
navigator.serviceWorker.register('sw.js', {
  scope: '/app/'
});
```
For this example the serve worker will control any files and sub directories of the scope but nothing above in the tree. Usually there's no need to set the scope, just place the sw file in the proper folder.

As of 2018 most browsers support service workers and there shouldn't be a problem implementing but I think it is still a good idea to check for browser support when implementing so here how we can do that: 

``` javascript 
if (navigator.serviceWorker) {
  navigator.serviceWorker.register('sw.js');
}
```

If the browser doesn't support service workers the navigator.serviceWorker value will be `undefined` which is a falsy value and the browser will skip everything contained in the if statement.

## Event Listeners

The service worker receives events and therefore we can add `eventListeners` to the service worker in order to complete certain tasks. 

### Fetch Event Listener

When the user navigates to a page within the service worker's scope, it controlls the page's actions. The network's request for the HTML goes to the service worker and triggers a `fetch` event. But that doesn't happen only for the HTML, a `fetch` event is triggered for every request sent by that page (Ie. images, css, js, etc).

Adding the fetch event listener to the service worker:

``` javascript
  self.addEventListener('fetch', function(event) {
    // do something
  });
```
self here refers to the service worker object. Once a `fetch` event is triggered we can access that returned data and interact with it.


## Service Worker Lifecycle

