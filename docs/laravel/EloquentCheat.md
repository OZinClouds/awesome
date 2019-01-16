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
// there is a method in ThreadsController, then 
if (method_exists($this,  $filter)) {
$this->$filter($value);
}
}
return  $this->builder;
}

// Fetch all relevant filters from the request.
public  function  getFilters()
{
// get only the desired querystring
return  array_filter($this->request->only($this->filters));
}
```  
### ThreadsFilter class extending Filters

```php
protected $filters = ['by'];
protected  function  by($username)
{
$user =  User::where('name', $username)->firstOrFail();
return  $this->builder->where('user_id', $user->id);
}
```
### Thread model

```php
public function scopeFilter($query, ThreadFilters $filters)
{
return $filters->apply($query);
}
```
### ThreadsController
```php
protected  function  getThreads(Channel $channel, ThreadFilters $filters)
{
$threads =  Thread::latest()->filter($filters);
  
if ($channel->exists) {
$threads->where('channel_id', $channel->id);
}
return $threads->get();
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjYyMjE4NjA1LDE0NTgzNTIxMTddfQ==
-->