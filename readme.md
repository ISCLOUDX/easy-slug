# EasySlug (Laravel Package)

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/e072de49-18e4-4dba-81c4-02705fe32467/small.png)](https://insight.sensiolabs.com/projects/e072de49-18e4-4dba-81c4-02705fe32467)

## Quick start

EasySlug provides a flexible way to create slugs.
It is compatible with both **Laravel4** as well as **Laravel5**

## Installation

In order to install EasySlug, just add 

    "easy-slug/easy-slug": "2.*"

to your composer.json. Then run `composer install` or `composer update`.

Then in your `config/app.php` add 

    'EasySlug\EasySlug\EasySlugServiceProvider',
    
in the providers array and

    'EasySlug' => 'EasySlug\EasySlug\EasySlugFacade'
    
to the `aliases` array.

## Simple Slug with validation from database

You can make a simple slug with DB validation using following code

```php
<?php

/**
 *@param1            => The string to be slugged
 *@param2            => The table name where slug is stored
 *@param3 (Optional) => The column name of slug. If not specified, by default "slug" is considered
 *@param4 (Optional) => The separator of slug. If not specified, by default "-" is taken
 */

EasySlug::generateUniqueSlug('Your String', 'table name', $column = "slug", $separator = '-')
```

This function looks for similar slugs in the table/column name specified in parameters.
If slugs with similar pattern are found it appends numeric digits at the end of slug as follows :

    my-string-slug
    my-string-slug-2
    my-string-slug-3
    my-string-slug-4

## Simple Slug without database validation

You can also make a simple slug with string as a input

```php
<?php

EasySlug::generateSlug('Your String', $separator = '-')
```

## License

EasySlug is free software distributed under the terms of the MIT license
