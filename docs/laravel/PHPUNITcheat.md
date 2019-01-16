# PHPUNIT Cheat


in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```php
if (app()->environment() === 'testing') throw $exception;
```
*better way* is to use in TestCase the gist from @adamwathan
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY2NDM3MDY3NywtMTE0NjI1MDMyMF19
-->