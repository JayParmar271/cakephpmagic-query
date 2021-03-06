# MagicQuery plugin for CakePHP

[![Latest Stable Version](https://poser.pugx.org/JayParmar271/cakephp-magic-query/v/stable)](https://packagist.org/packages/JayParmar271/cakephp-magic-query)
[![Total Downloads](https://poser.pugx.org/JayParmar271/cakephp-magic-query/downloads)](https://packagist.org/packages/JayParmar271/cakephp-magic-query)
[![License](https://poser.pugx.org/JayParmar271/cakephp-magic-query/license)](https://packagist.org/packages/JayParmar271/cakephp-magic-query)
![Tests](https://github.com/JayParmar271/cakephp-magic-query/workflows/Run%20tests/badge.svg?branch=master)
![PHPStan Check](https://github.com/JayParmar271/cakephp-magic-query/workflows/Run%20PHPStan/badge.svg?branch=master)
![Coding Style Check](https://github.com/JayParmar271/cakephp-magic-query/workflows/Coding%20Style/badge.svg?branch=master)


Simple query builder made with CakePHP

## Requirements
- CakePHP 3.5+ 

## Installation

You can install this plugin into your CakePHP application using [composer](https://getcomposer.org).

The recommended way to install composer packages is:

```
composer require jayparmar271/cakephp-magic-query
```

## Usage
1. Add behavior in your table. (../src/Model/Table/UsersTable.php)

```
    $this->addBehavior('MagicQuery.Query');
```

2. Use getRecord() to get single record.

```
    $this->Users->getRecord(['name'], ['id' => '1']);
```   

### To set default options:
1. Create new config file and add your default options. (/config/magic_query.php)

```php
return [
  'MagicQuery' => [
    'limit' => 2,
    'page' => 1,
    'orderBy' => ['id' => 'ASC'],
    'hydrate' => false,
    'validate' => true,
  ],
];
```

2. Load into your bootstrap.php (/config/bootstrap.php)

```php
/*
 * Load magic query file
 */
if (file_exists(CONFIG . 'magic_query.php')) {
    Configure::load('magic_query');
}
```

That's all. Enjoy!

You can find more examples [here](EXAMPLES.md).

## License
The MIT License. Please see [License](LICENSE) File for more information.
