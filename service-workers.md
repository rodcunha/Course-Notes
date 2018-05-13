# Service Workers

## Registering a service worker

To register a service worker we will need to use the navigator.serviceWorker method register and give it a path like so:

``` javascript
navigator.serviceWorker.register('sw.js');
```

This will register the servie worker with the browser and returns a promise, you will then get callbacks for success and failure.§
