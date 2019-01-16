# View Cheat

* [composer] (#composer)

## Composer
View composers are callbacks or class methods that are called when a view is rendered.
```php
public  function  boot()
{

\View::composer('*', function ($view) {

$view->with('channels', Channel::all());

});
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3NjYyNDY3NV19
-->