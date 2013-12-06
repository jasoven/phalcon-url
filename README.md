phalcon-url
===========

Расширение класса \Phalcon\Mvc\Url для реализации обратных ссылок

Пример использования:

$router->add('/admin(/:controller((/{id:[0-9]+})?/:action)?)?', [
	'module'     => 'backend',
	'controller' => 2,
	'action'     => 6,
	'id'         => 5,
])->setName('default');

...

$this->_di->set('url', function () use ($config)
{
	return new \Library\URL();
});

...

<a href="<?= $this->url->route('default', ['controller'=>'users']); ?>"></a> // => /admin/users
<a href="<?= $this->url->route('default', ['controller'=>'users', 'action'=>'list']); ?>"></a> // => /admin/users/list
<a href="<?= $this->url->route('default', ['controller'=>'users', 'action'=>'edit', 'id'=>1]); ?>"></a> // => /admin/users/1/edit