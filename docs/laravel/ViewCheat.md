# View Cheat

* [composer] (#composer)

## Composer
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
eyJoaXN0b3J5IjpbLTEzMjM1MTE4NDddfQ==
-->