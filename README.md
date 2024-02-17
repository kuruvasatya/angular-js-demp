# angular-js-demp

```
/angularjs-sample-app
│
├── index.html
├── js
│   ├── angular.min.js
│   ├── angular-route.min.js
│   ├── app.js
│   ├── controllers
│   │   ├── HomeController.js
│   │   ├── AboutController.js
│   │   └── CareerController.js
│   └── directives
│       ├── headerDirective.js
│       └── footerDirective.js
│
└── views
    ├── header.html
    ├── footer.html
    ├── home.html
    ├── about.html
    └── career.html
```

## index.html

```
<!DOCTYPE html>
<html lang="en" ng-app="myApp">
<head>
    <meta charset="UTF-8">
    <title>AngularJS Sample App</title>
    <script src="js/angular.min.js"></script>
    <script src="js/angular-route.min.js"></script>
</head>
<body>

<app-header></app-header>

<content ng-view></content>

<app-footer></app-footer>

<script src="js/app.js"></script>
<script src="js/controllers/HomeController.js"></script>
<script src="js/controllers/AboutController.js"></script>
<script src="js/controllers/CareerController.js"></script>
<script src="js/directives/headerDirective.js"></script>
<script src="js/directives/footerDirective.js"></script>

</body>
</html>

```

## views/header.html
```
<header>
    <nav>
        <ul>
            <li><a href="#/">Home</a></li>
            <li><a href="#/about">About Us</a></li>
            <li><a href="#/career">Career</a></li>
        </ul>
    </nav>
</header>

```

## views/footer.html
```
<footer>
    <p>&copy; 2024 My AngularJS App</p>
</footer>
```

## js/app.js

```
angular.module('myApp', ['ngRoute'])
.config(function($routeProvider) {
    $routeProvider
    .when('/', {
        templateUrl: 'views/home.html',
        controller: 'HomeController'
    })
    .when('/about', {
        templateUrl: 'views/about.html',
        controller: 'AboutController'
    })
    .when('/career', {
        templateUrl: 'views/career.html',
        controller: 'CareerController'
    })
    .otherwise({ redirectTo: '/' });
});

```

## js/controller/HomeController.js
```
angular.module('myApp')
.controller('HomeController', function($scope) {
    $scope.message = 'Welcome to Home';
});

```

## js/controller/AboutController.js
```
angular.module('myApp')
.controller('AboutController', function($scope) {
    $scope.message = 'About Us';
});
```

## js/controller/CareerController.js
```
angular.module('myApp')
.controller('CareerController', function($scope) {
    $scope.message = 'Career';
});
```

## js/directives/HeaderDirective.js
```
angular.module('myApp').directive('appHeader', function() {
    return {
        restrict: 'E',
        templateUrl: 'views/header.html'
    };
});
```
## js/directives/FooterDirective.js
```
angular.module('myApp').directive('appFooter', function() {
    return {
        restrict: 'E',
        templateUrl: 'views/footer.html'
    };
});
```
