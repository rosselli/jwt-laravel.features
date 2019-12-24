# JWT Laravel

[LaraShout](https://www.larashout.com/laravel-6-jwt-authentication)


```composer require tymon/jwt-auth:dev-develop --prefer-source```

```php artisan vendor:publish # select 8 (Provider: Tymon\JWTAuth\Providers\LaravelServiceProvider)```


```
'providers' => [
    ....
    'Tymon\JWTAuth\Providers\JWTAuthServiceProvider',
],
'aliases' => [
    ....
    'JWTAuth' => 'Tymon\JWTAuth\Facades\JWTAuth',
        'JWTFactory' => 'Tymon\JWTAuth\Facades\JWTFactory',
],
```

To publish the configuration file in Laravel, you need to run following line of code :

```php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\JWTAuthServiceProvider"```

Now for token encryption, I need to generate a secret key by running following line of code :

```php artisan jwt:generate```