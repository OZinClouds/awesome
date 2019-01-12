# PHPUNIT Cheat


in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```

if (app()->environment() === 'testing') throw $exception;
        
```





> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI5MzY5ODYzNV19
-->