# Laravel Sugars
* [Factory for DB Notifications](#factory-for-db-notifications)
*  [View Composer](#view-composer)

## Factory for DB Notifications
```php
$factory->define(\Illuminate\Notifications\DatabaseNotification::class, function ($faker) {
    return [
        'id' => \Ramsey\Uuid\Uuid::uuid4()->toString(),
        'type' => 'App\Notifications\ThreadWasUpdated',
        'notifiable_id' => function () {
            return auth()->id() ?: factory('App\User')->create()->id;
        },
        'notifiable_type' => 'App\User',
        'data' => ['foo' => 'bar']
    ];
});
```

## View Composer
View composers are callbacks or class methods that are called when a view is rendered.  
Lifecycle is important. Prevents calling same queries in each page...
**example:** 
* in AppServiceProvider, boot method,
* in all pages (*) send the page the whole Channel collection (::all()...)
```php
public  function  boot()
{
\View::composer('*', function ($view) {
$view->with('channels', Channel::all());
});
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3Nzk4MTk1OTMsMTM4ODIwNTg1M119
-->