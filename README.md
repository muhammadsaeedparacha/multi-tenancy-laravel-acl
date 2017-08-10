# Laravel ACL

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Build Status][ico-travis]][link-travis]
[![Coverage Status][ico-scrutinizer]][link-scrutinizer]
[![Quality Score][ico-code-quality]][link-code-quality]
[![Total Downloads][ico-downloads]][link-downloads]

Multi Tenant Laravel ACL is a simple User - Company - role, permission ACL for SaaS Applications in Laravel Framework.
This package was based on the great package [Caffeinated/Shinobi](https://github.com/yajra/laravel-acl) but is catered to Multi-Database Multi-Tenant SaaS applications.

## Documentations
- [Laravel ACL][link-docs]

## Installation

Via Composer

``` bash
$ composer require yajra/laravel-acl:^3.0
```

## Configuration
Register service provider:
``` php
Yajra\Acl\AclServiceProvider::class
```

Register Middlewares: in App\Http\Kernel.php
```php
'canAtLeast' => \Yajra\Acl\Middleware\CanAtLeastMiddleware::class,
'permission' => \Yajra\Acl\Middleware\PermissionMiddleware::class,
'role' => \Yajra\Acl\Middleware\RoleMiddleware::class,
```

Define User Trait in User Model
```php
...
use Yajra\Acl\Traits\HasRoleAndPermission;

class User extends Authenticatable
{
	...
	use HasRoleAndPerimssions; 
	...
}
```

Publish assets:
```php
$ php artisan vendor:publish --tag=laravel-acl
```

Run migrations:
```php
php artisan migrate
```

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) and [CONDUCT](CONDUCT.md) for details.

## Security

If you discover any security related issues, please email aqangeles@gmail.com instead of using the issue tracker.

## Credits

- [Arjay Angeles][link-author]
- [Caffeinated/Shinobi](https://github.com/caffeinated/shinobi)
- [All Contributors][link-contributors]

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/muhammadsaeedparacha/multi-tenant-laravel-acl.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/yajra/laravel-acl/master.svg?style=flat-square
[ico-scrutinizer]: https://img.shields.io/scrutinizer/coverage/g/yajra/laravel-acl.svg?style=flat-square
[ico-code-quality]: https://img.shields.io/scrutinizer/g/yajra/laravel-acl.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/yajra/laravel-acl.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/muhammadsaeedparacha/multi-tenant-laravel-acl
[link-travis]: https://travis-ci.org/yajra/laravel-acl
[link-scrutinizer]: https://scrutinizer-ci.com/g/yajra/laravel-acl/code-structure
[link-code-quality]: https://scrutinizer-ci.com/g/muhammadsaeedparacha/multi-tenant-laravel-acl
[link-downloads]: https://packagist.org/packages/muhammadsaeedparacha/multi-tenant-laravel-acl
[link-author]: https://github.com/muhammadsaeedparacha
[link-contributors]: ../../contributors
[link-docs]: https://yajrabox.com/docs/laravel-acl/3.0
