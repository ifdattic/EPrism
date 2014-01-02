EPrism
======

**EPrism** is an extension for Yii framework. This extension is a wrapper for [Prism][prism-js-link] by [Lea Verou][lea-verou-homepage]. *Prism* is a lightweight, extensible syntax highlighter, built with modern web standards in mind. This extension adds this great syntax highlighter using a `widget()` method.

Requirements
------------

* Yii 1.1 or above (tested on 1.1.14)

Installation
------------

### Composer

**EPrism** can be installed using a [Composer][composer-link].

Run the following command:

```shell
php composer.phar require ifdattic/eprism "dev-master"
```

or make sure you have the following code in *composer.json* file:

```json
{
    "require": {
        "ifdattic/eprism": "dev-master"
    }
}
```

### Manual installation

Download the latest version of extension, extract & place it in your project (*extensions* directory or any of your choice). Just make sure to adjust path for loading it.

Usage
-----

Place the following code inside your view file:

```php
<?php $this->widget('vendor.ifdattic.eprism.EPrism'); ?>
```

Default options can be changed by sending an array as a second parameter:

```php
<?php $this->widget(
    'vendor.ifdattic.eprism.EPrism',
    [
        // Default values for properties
        'manualHighlight' => false,
        'scriptPosition' => null,
        'cssFile' => null,
        'scriptFile' => null,
    ]
); ?>
```

The explanation of options:

* **manualHighlight** - The flag which disables automatic highlighting. If automatic highlighting is disabled, the highlight will have to be initiated manually using JavaScript.
* **scriptPosition** - The position of the script ([`registerScriptFile()` method documentation][registerscriptfile-documentation-link])
* **cssFile** - The CSS file used by the highlighter. Available options:
    - *false* - CSS file won't be registered.
    - *null* - the default CSS file will be registered.
    - *string* - defined file will be registered.
* **scriptFile** - The JS file used by the highlighter. Available options:
    - *false* - JS file won't be registered.
    - *null* - the default JS file will be registered.
    - *string* - defined file will be registered.

Here's the example using different values for extension:

```php
<?php $this->widget(
    'vendor.ifdattic.eprism.EPrism',
    [
        // Only values you want to change need to be sent
        'manualHighlight' => true,
        'scriptPosition' => CClientScript::POS_END,
        'cssFile' => 'prism/prism.css',
        'scriptFile' => false,
    ]
); ?>
```

Resources
---------

* [Prism syntax highlighter (contains demo)][prism-js-link]
* [Demo of extension][yii-extension-demo]
* [Issue tracker for extension][issues-of-extension]
* [Issue tracker for syntax highlighter][issues-of-highlighter]

Notes
-----

* For convenience extension contains CSS & JS assets, but you will probably want to [generate][prismjs-download-page] those files for your own needs and include them in the project.

[prism-js-link]: http://prismjs.com
[lea-verou-homepage]: http://lea.verou.me
[registerscriptfile-documentation-link]: http://www.yiiframework.com/doc/api/1.1/CClientScript/#registerScriptFile-detail
[prismjs-download-page]: http://prismjs.com/download.html
[yii-extension-demo]: http://ifdattic.com/blog/2-converting-px-ems-less
[issues-of-extension]: https://github.com/ifdattic/EPrism/issues
[issues-of-highlighter]: https://github.com/LeaVerou/prism/issues
