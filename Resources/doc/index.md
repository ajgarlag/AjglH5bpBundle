AjglH5bpBundle
==============

The AjglH5bpBundle provides a frontend twig template for your **Symfony2**
application powered by the [HTML5 ★ Boilerplate](http://html5boilerplate.com/)
project

## Prerequisites

This version of the bundle has been tested with Symfony 2.1 and depends on
AjglJQueryBundle


## Installation

Installation is a quick process:

1. Download AjglH5bpBundle using composer
2. Enable the Bundle
3. Register the bundle in the assectic configuration

### Step 1: Download AjglH5bpBundle using composer

Add AjglH5bpBundle in your composer.json:

```js
{
    "require": {
        "ajgl/h5bp-bundle": "*"
    }
}
```

Now tell composer to download the bundle by running the command:

``` bash
$ php composer.phar update ajgl/h5bp-bundle
```

Composer will install the bundle to your project's `vendor/ajgl` directory.

### Step 2: Enable the bundle

Enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Ajgl\Bundle\H5bpBundle\AjglH5bpBundle(),
    );
}
```

### Step 3: Register the bundle in the assectic configuration

The bundle must be registered in the assetic configuration:

``` yaml
assetic:
    // ...
    bundles:        [ AjglH5bpBundle ]
            ....
```

Next Steps
----------

Now that you have completed the basic installation you should extend
the base twig template
```
{% extends "AjglH5bpBundle::h5bp.base.html.twig" %}
```

Available variables
-------------------
The template uses some variables that you can optionally redefine to customize its behaviour. Here's the complete list:

 - **h5bp_html_classes**: allows you to set custom classes to the html tag.
 - **h5bp_body_classes**: allows you to set custom classes to the body tag.
 - **h5bp_analytics_id**: allows you to specify your google analytics id. If you don't provide a value for this variable the whole Google analytics script won't be added on the resulting page.


Configure Google Analytics
--------------------------
Google analytics is disabled by default. You can easily enable it
by passing your analytics id within the variable "h5bp_analytics_id".
Anyway I suggest you to set this variable directly in your configuration
file among the Twig global variables. This way you have the opportunity
to specify an id on the environments you prefer to: for example you may
want to not use analytics on development but to use it in production,
so just add the following lines on your config_prod.yml file
```yaml
twig:
    globals:
        h5bp_analytics_id: UAXXXXXXXX1
```
