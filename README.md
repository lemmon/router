# Lemmon Router

**Lemmon Router** is a lightweight standalone routing library for PHP 7.

* Flexible regular expression routing
* Simple and lightweight
* Fast (100k requests/second)
* Mod_Rewrite is not required, although supported; extreme portability for rapid development

## Getting started

1. PHP 7.x is required
2. Install Lemmon Router using [Composer](#composer-installation) (recommended) or manually

## Composer Installation

1. Get [Composer](http://getcomposer.org/)
2. Require Lemmon Router with `php composer.phar require lemmon/router`
3. Add the following to your application's main PHP file: `require 'vendor/autoload.php';`

## Example

```php
<?php
require_once __DIR__ . '/vendor/autoload.php';

$r = new Lemmon\Router\SimpleRouter;

$r->match('hello-world', function() {
    echo 'Hello World!';
});
```

*Example 1* - Respond to all requests

```php
$r->match(function() {
    echo 'Everything';
});
```

*Example 2* - Match parameters

```php
$r->match('{controller}/{action}', function($r, $m) {
    echo 'Controller ' . $m['controller'] . ' / Action: ' . $m['action'];
});
```
