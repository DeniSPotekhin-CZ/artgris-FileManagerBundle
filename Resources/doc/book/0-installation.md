Chapter 0. Installation and your first File Manager
===================================================

FileManager Project is a simple Multilingual File Manager Bundle for symfony

Installation
------------

### Step 1: Download the Bundle

```bash
$ composer require artgris/filemanager-bundle
```

### Step 2: Enable the Bundle

```php
<?php
// app/AppKernel.php

// ...
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Artgris\Bundle\FileManagerBundle\ArtgrisFileManagerBundle(),
        );
    }

    // ...
}
```
### Step 3: Load the Routes


```yaml
# app/config/routing.yml
artgris_bundle_file_manager:
    resource: "@ArtgrisFileManagerBundle/Controller"
    type:     annotation
    prefix:   /manager
```

### Step 4: Prepare the Web Assets

```cli
# Symfony 3
php bin/console assets:install --symlink
```

### Step 5:  Enable the translator service 

```yml
# app/config/config.yml
framework:
    translator: { fallbacks: [ "en" ] }
```    
    
Creating Your First File Manager
---------------------------------

Create a folder **uploads** in **web**.
 
####Add following min configuration :

```yaml
# app/config/config.yml
artgris_file_manager:
    conf:
        default:
            dir: "../web/uploads"
```

You can now access the file manager under the path: 

    http://your-host/app_dev.php/manager/?conf=default
    
    
<img src="https://raw.githubusercontent.com/artgris/FileManagerBundle/master/Resources/doc/images/filemanger-default.png" alt="Symfony Filemanager created with FileManagerBundle" />


-------------------------------------------------------------------------------

[Chapter 1. Basic Configuration](1-basic-configuration.md) &rarr;