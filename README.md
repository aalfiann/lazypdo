# LazyPDO

[![Latest Stable Version](https://img.shields.io/packagist/v/aalfiann/lazypdo.svg)](https://packagist.org/packages/aalfiann/lazypdo)
[![Total Downloads](https://img.shields.io/packagist/dt/aalfiann/lazypdo.svg)](https://packagist.org/packages/aalfiann/lazypdo)
[![License](https://poser.pugx.org/aalfiann/sitemap-manager/license)](https://github.com/aalfiann/lazypdo/blob/HEAD/LICENSE.md)

A PHP class to make lazy load PDO connection to database.  
You can use LazyPDO to replace the default PDO, when you need to lazy load. No database connection will be made until first call to one of PDO's methods.

## Installation

Install this package via [Composer](https://getcomposer.org/).
```
composer install aalfiann/lazypdo
```

## Usage

```php
require 'vendor/autoload.php';
use aalfiann\LazyPDO;

$dsn = 'mysql:hostname=localhost;dbname=test';
$user = 'test';
$password = 'test';

$pdo = new LazyPDO($dns, $user, $password); // doesn't connect yet

$pdo->query('SELECT * FROM `table` WHERE 1'); // connection is made before executing query
```