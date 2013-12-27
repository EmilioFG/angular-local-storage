angular-local-storage
=====================

An Angular module that gives you access to the browsers local storage

Remember to set your app name (settings.appPrefix) in the settings at the beginning of angular-local-storage.js:

```javascript
angular.module('LocalStorageModule').value('prefix', 'myPre');
angular.module('testApp', ['LocalStorageModule'])
  .config(function ($routeProvider) {
    ....
});
```

To do:
- Add tests
- Expand Readme

Example use: 

```javascript
angular.module('yourModule', ['LocalStorageModule'])
.controller('yourCtrl', [
  '$scope',
  'localStorageService',
  function($scope, localStorageService) {
    // Start fresh
    localStorageService.clearAll();
    localStorageService.add('Favorite Sport','Ultimate Frisbee');
}]);

/*
To set the prefix of your localStorage name, you can use the setPrefix method 
available on the localStorageServiceProvider
*/
angular.module('yourModule', ['LocalStorageModule'])
.config(['localStorageServiceProvider', function(localStorageServiceProvider){
  localStorageServiceProvider.setPrefix('newPrefix');
});
```
Check out the full demo and documentation at http://gregpike.net/demos/angular-local-storage/demo.html
