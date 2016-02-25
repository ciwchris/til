When a promise is being returned by a function in a service a controller, which uses the service
when it is being created, can be tested by injecting the service during the controller creation and
assigning the function which will be called to a stubbed function. The stubbed function can then use
the $q service to either return a resolved or rejected promise. The $rootScope also needs to be
injected so that a digest cycle can be triggered, which will process the promise.

```javascript
beforeEach(function() {
    inject(function($controller, $q, $rootScope, someService) {
        someService.someMethod = function() { return $q.resolve({}); }
        sut = $controller(SomeCtrl');

        $rootScope.$digest();
    });
});
```
