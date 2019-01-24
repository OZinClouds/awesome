# Laravel Sugars
* [Factory for DB Notifications](#factory-for-db-notifications)

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4ODIwNTg1M119
-->