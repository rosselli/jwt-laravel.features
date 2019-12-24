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

12. Creating and Config Controllers, Models, FormRequest


13. Testing
```
# register
curl -X POST -H 'Content-Type: application/json' -d '{"name":"John","email":"john@aa.com","password":"john123"}' http://localhost:8000/api/register

{"success":true,"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9yZWdpc3RlciIsImlhdCI6MTU3NzE3MTg0MiwiZXhwIjoxNTc3MTc1NDQyLCJuYmYiOjE1NzcxNzE4NDIsImp0aSI6ImEwd2ZFdldDZmZRUUNUSGgiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.1CGO_yAy8SSVH3fYfzfn6pYKIio1n4UVhjFzbVs1HF8"}

# login
curl -X POST -H 'Content-Type: application/json' -d '{"email":"john@aa.com","password":"john123"}' http://localhost:8000/api/login

{"success":true,"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9sb2dpbiIsImlhdCI6MTU3NzE3MjAwOCwiZXhwIjoxNTc3MTc1NjA4LCJuYmYiOjE1NzcxNzIwMDgsImp0aSI6InVhVTNvM3Y3eXFQTGVXUDYiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.iJ0X8WRg4MqS23tPfSQm475UyMOiTHgqPu3dEe9cQLQ"}

# tasks insert
curl -X POST -H 'Content-Type: application/json' -d '{"title":"JWT Task","description":"Testing Tasks Insert","token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9sb2dpbiIsImlhdCI6MTU3NzE3MjAwOCwiZXhwIjoxNTc3MTc1NjA4LCJuYmYiOjE1NzcxNzIwMDgsImp0aSI6InVhVTNvM3Y3eXFQTGVXUDYiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.iJ0X8WRg4MqS23tPfSQm475UyMOiTHgqPu3dEe9cQLQ"}' http://localhost:8000/api/tasks


```





