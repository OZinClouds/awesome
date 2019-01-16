# PHPUNIT Cheat


in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```php
if (app()->environment() === 'testing') throw $exception;
```
*better way* is to use 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNDYyNTAzMjBdfQ==
-->