# JWT Laravel

[LaraShout](https://www.larashout.com/laravel-6-jwt-authentication)

1. Install
```
composer require tymon/jwt-auth:dev-develop --prefer-source
```

2. Publish
```
php artisan vendor:publish # select 8 (Provider: Tymon\JWTAuth\Providers\LaravelServiceProvider)
```

3. Generating JWT Authentication Keys
```
php artisan jwt:secret
```

4. Register the Middleware
```
# app/Http/Kernel.php
protected $routeMiddleware = [
    'auth.jwt'  =>  \Tymon\JWTAuth\Http\Middleware\Authenticate::class,
];
```
5. Setting Up API Routes

6. Updating User Model

7. Creating Registration Form Request
```
php artisan make:request RegistrationFormRequest
```

8. Creating API Controller for Login and Registration
```
php artisan make:controller APIController
```

9. Task Model and Migration
```
php artisan make:model Task -mc
```

10. Create and Config Database
```
sqlite3 database/database.sqlite
```

11. Migrate
```
php artisan migrate
``
