# JWT Laravel

This implementation is based on [LaraShout](https://www.larashout.com/laravel-6-jwt-authentication)'s article.

**1. Install** ``` composer require tymon/jwt-auth:dev-develop --prefer-source ```

**2. Publish** 
``` 
php artisan vendor:publish 
# select 8 (Provider: Tymon\JWTAuth\Providers\LaravelServiceProvider) 
```

**3. Generating JWT Authentication Keys** ``` php artisan jwt:secret ```

**4. Register the Middleware**
```
# app/Http/Kernel.php
protected $routeMiddleware = [
    'auth.jwt'  =>  \Tymon\JWTAuth\Http\Middleware\Authenticate::class,
];
```

**5. Setting Up API Routes**

**6. Updating User Model**

**7. Creating Registration Form Request** ``` php artisan make:request RegistrationFormRequest ```

**8. Creating API Controller for Login and Registration** ``` php artisan make:controller APIController ```

**9. Task Model and Migration** ``` php artisan make:model Task -mc ```

**10. Create and Config Database** ``` sqlite3 database/database.sqlite ```

**11. Migrate** ``` php artisan migrate ```

**12. Creating and Config Controllers, Models, FormRequest**

**13. Testing**
```
# register
curl -X POST -H 'Content-Type: application/json' -d '{"name":"John","email":"john@aa.com","password":"john123"}' http://localhost:8000/api/register

# login
curl -X POST -H 'Content-Type: application/json' -d '{"email":"john@aa.com","password":"john123"}' http://localhost:8000/api/login

# tasks insert
curl -X POST -H 'Content-Type: application/json' -d '{"title":"JWT Task","description":"Testing Tasks Insert","token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9sb2dpbiIsImlhdCI6MTU3NzE3MjAwOCwiZXhwIjoxNTc3MTc1NjA4LCJuYmYiOjE1NzcxNzIwMDgsImp0aSI6InVhVTNvM3Y3eXFQTGVXUDYiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.iJ0X8WRg4MqS23tPfSQm475UyMOiTHgqPu3dEe9cQLQ"}' http://localhost:8000/api/tasks

# tasks list
curl 'http://127.0.0.1:8000/api/tasks?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9sb2dpbiIsImlhdCI6MTU3NzE3MjAwOCwiZXhwIjoxNTc3MTc1NjA4LCJuYmYiOjE1NzcxNzIwMDgsImp0aSI6InVhVTNvM3Y3eXFQTGVXUDYiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.iJ0X8WRg4MqS23tPfSQm475UyMOiTHgqPu3dEe9cQLQ'

```





