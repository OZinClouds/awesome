# PHPUNIT Cheat
* [Handling Exceptions](Handling-Exceptions)

## Handling Exceptions
in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```php
if (app()->environment() === 'testing') throw $exception;
```
*better way* is to use in *TestCase* the gist from :link:[@adamwathan](https://gist.github.com/adamwathan/125847c7e3f16b88fa33a9f8b42333da) => **Disabling Exception Handling in Laravel Feature Tests**

---

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxNjk4Njg5OCwxNjY0MzcwNjc3LC0xMT
Q2MjUwMzIwXX0=
-->