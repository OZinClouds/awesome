# PHPUNIT Cheat


in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```php
if (app()->environment() === 'testing') throw $exception;
```
*better way* is to use in TestCase the gist from [@adamwathan](https://gist.github.com/adamwathan/125847c7e3f16b88fa33a9f8b42333da) => Disabling Exception Handling in Laravel Feature Tests
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDkzMDcwMDk2LDE2NjQzNzA2NzcsLTExND
YyNTAzMjBdfQ==
-->