# PHPUNIT Cheat
* [Disable Telescope](#disable-telescope)
* [DB in memory](#db-in-memory)
* [tap for grouping](#tap-for-grouping)


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
## tap for grouping
good practice to group assertions in a tap.

```php
tap($user->fresh(), function ($user) {
$this->assertTrue($user->something);
$this->assertNull($user->anotherthing);
});
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU1OTU0NTkyOCwtNTcwNzc0NTcxLC0xNT
E2NTkzOTY0LDE2NjQzNzA2NzcsLTExNDYyNTAzMjBdfQ==
-->