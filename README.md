phalcon-url
===========

Расширение класса \Phalcon\Mvc\Url для реализации обратных ссылок

Пример использования:

```php
$router->add('/admin(/:controller((/{id:[0-9]+})?/:action)?)?', [
	'module'     => 'backend',
	'controller' => 2,
	'action'     => 6,
	'id'         => 5,
])->setName('default');
```

...

```php
$this->_di->set('url', function () use ($config)
{
	return new \Library\URL();
});
```

...

```php
<a href="<?= $this->url->route('default', ['controller'=>'users']); ?>"></a> // => /admin/users
```
```php
<a href="<?= $this->url->route('default', ['controller'=>'users', 'action'=>'list']); ?>"></a> // => /admin/users/list
```
```php
<a href="<?= $this->url->route('default', ['controller'=>'users', 'action'=>'edit', 'id'=>1]); ?>"></a> // => /admin/users/1/edit
```
