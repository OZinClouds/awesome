# Eloquent Cheat



## Scope Filters for get requests
* from Laracasts [Forum TDD Lesson](https://laracasts.com/series/lets-build-a-forum-with-laravel/episodes/15?autoplay=true)
* [github HEAD for lesson 15](https://github.com/laracasts/Lets-Build-a-Forum-in-Laravel/commit/3685b0f968927db371e48d7281b25ff751c120a3?diff=unified)
* Given there is a set of threads in a forum, when filtered by (current) user, then list user's threads
  
### abstract Filters class
```php
protected $request;
protected $builder;
protected $filters = [];
public  function  __construct(Request $request)
{
$this->request = $request;
}

// apply filters
public  function  apply($builder)
{
$this->builder = $builder;
foreach ($this->getFilters() as $filter => $value) {
if (method_exists($this,  $filter)) {
$this->$filter($value);
}
}
return  $this->builder;
}

// Fetch all relevant filters from the request.
public  function  getFilters()
{
return  array_filter($this->request->only($this->filters));
}
```  
### ThreadsFilter class extending Filters

```php

```
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTI1NjM3OTIzLDE0NTgzNTIxMTddfQ==
-->