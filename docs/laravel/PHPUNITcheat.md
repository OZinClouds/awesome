# PHPUNIT Cheat
* [Handling Exceptions](#handling-exceptions)
* [Disable Telescope](#disable-telescope)
* [DB in memory](#db-in-memory)

## Handling Exceptions
in Handler.php (Exceptions) - function report => invoke to throw exceptions when in testing environment:
```php
if (app()->environment() === 'testing') throw $exception;
```
*better way* is to use in *TestCase* the gist from :link:[@adamwathan](https://gist.github.com/adamwathan/125847c7e3f16b88fa33a9f8b42333da) => **Disabling Exception Handling in Laravel Feature Tests**

---
## Disable Telescope
Telescope interferes with testing and better be disabled in PHPUNIT.xml
```xml
<env name="TELESCOPE_ENABLED" value="false"/>`
```
## DB in Memory
Add sqlite and :memory: in PHPUNIT.xml  
In test classes use DatabaseMigrations
	`use DatabaseMigrations`
```xml
<env name="DB_CONNECTION" value="sqlite"/>
<env name="DB_DATABASE" value=":memory:"/>
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MTY1OTM5NjQsMTY2NDM3MDY3NywtMT
E0NjI1MDMyMF19
-->