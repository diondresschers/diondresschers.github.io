<img src="../static/amsterdam_umc_logo_rgb.svg" height="50%" width="50%" style="display: block; margin-left: auto;
 margin-right: auto; width: 50%;">
<p style="text-align:center; font-size: 200%;">Apotheek</p>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fork-awesome@1.1.7/css/fork-awesome.min.css" integrity="sha256-gsmEoJAws/Kd3CjuOQzLie5Q3yshhvmo7YNtBG7aaEY=" crossorigin="anonymous">

* Licentie: <i class="fa fa-creative-commons" aria-hidden="true"></i> CC BY-SA 4.0
* By: Dion Dresschers
* Date: 2020-06-19
* Version: 2020-06-19 14:11:48

# Symfony 4 Cheat Sheet

--- 

## update 

## update a patch and minor version

`composer update "symfony/*" --with-all-dependencies`

## Mandatory software

* >= PHP7.1 
* Composer

## Check Software

## Check Software - Check PHP

`root@ubuntu-vm:/var/www/localhost/wordpress/diontest# php --version`

`
PHP 7.2.24-0ubuntu0.18.04.6 (cli) (built: May 26 2020 13:09:11) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.2.24-0ubuntu0.18.04.6, Copyright (c) 1999-2018, by Zend Technologies
`

## Check Software - Check Linux

`root@ubuntu-vm:/var/www/localhost/wordpress/diontest# cat etc/*release*`

`
cat: 'etc/*release*': No such file or directory
root@ubuntu-vm:/var/www/localhost/wordpress/diontest# cat /etc/*release*
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=18.04
DISTRIB_CODENAME=bionic
DISTRIB_DESCRIPTION="Ubuntu 18.04.4 LTS"
NAME="Ubuntu"
VERSION="18.04.4 LTS (Bionic Beaver)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 18.04.4 LTS"
VERSION_ID="18.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=bionic
UBUNTU_CODENAME=bionic
`

## Check Software - Composer

`root@ubuntu-vm:/var/www/localhost/wordpress/diontest# composer`

`
Command 'composer' not found, but can be installed with:

apt install composer
`

`root@ubuntu-vm:/var/www/localhost/wordpress/diontest# apt install composer`

`
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following package was automatically installed and is no longer required:
  libegl1-mesa
Use 'apt autoremove' to remove it.
The following additional packages will be installed:
  jsonlint php-cli-prompt php-composer-ca-bundle php-composer-semver php-composer-spdx-licenses php-json-schema
  php-psr-log php-symfony-console php-symfony-debug php-symfony-filesystem php-symfony-finder
  php-symfony-polyfill-mbstring php-symfony-process
Suggested packages:
  fossil mercurial subversion php-symfony-event-dispatcher php-symfony-lock
Selecting previously unselected package php-symfony-process.
Preparing to unpack .../10-php-symfony-process_3.4.6+dfsg-1ubuntu0.1_all.deb ...
Unpacking php-symfony-process (3.4.6+dfsg-1ubuntu0.1) ...
Selecting previously unselected package php-symfony-filesystem.
Preparing to unpack .../11-php-symfony-filesystem_3.4.6+dfsg-1ubuntu0.1_all.deb ...
Unpacking php-symfony-filesystem (3.4.6+dfsg-1ubuntu0.1) ...
Selecting previously unselected package php-cli-prompt.
Preparing to unpack .../12-php-cli-prompt_1.0.3+dfsg-1_all.deb ...
Unpacking php-cli-prompt (1.0.3+dfsg-1) ...
Selecting previously unselected package composer.
Preparing to unpack .../13-composer_1.6.3-1_all.deb ...
Unpacking composer (1.6.3-1) ...
Setting up php-psr-log (1.0.2-1) ...
Setting up php-symfony-finder (3.4.6+dfsg-1ubuntu0.1) ...
Setting up php-composer-ca-bundle (1.1.0-1) ...
Setting up php-json-schema (5.2.6-1) ...
Setting up php-composer-semver (1.4.2-1) ...
Setting up php-cli-prompt (1.0.3+dfsg-1) ...
Setting up php-composer-spdx-licenses (1.3.0-1) ...
Setting up php-symfony-filesystem (3.4.6+dfsg-1ubuntu0.1) ...
Setting up php-symfony-polyfill-mbstring (1.6.0-2) ...
Setting up jsonlint (1.7.1-1) ...
Setting up php-symfony-process (3.4.6+dfsg-1ubuntu0.1) ...
Setting up php-symfony-debug (3.4.6+dfsg-1ubuntu0.1) ...
Setting up php-symfony-console (3.4.6+dfsg-1ubuntu0.1) ...
Setting up composer (1.6.3-1) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
`

`root@ubuntu-vm:/var/www/localhost/wordpress/diontest# composer --version`

`
Do not run Composer as root/super user! See https://getcomposer.org/root for details
Composer 1.6.3 2018-01-31 16:28:17
`

`dhdresschers@ubuntu-vm:/var/www/localhost$ composer --version`

`
Composer 1.6.3 2018-01-31 16:28:17
`

# Symfony Documentation

* [Coding Standards (Symfony 4.4 Docs)](https://symfony.com/doc/4.4/contributing/code/standards.html)
* [Installing & Setting up the Symfony Framework (Symfony 4.4 Docs)](https://symfony.com/doc/4.4/setup.html)
* [PHP: PHP Manual - Manual](https://www.php.net/manual/en/)
* 

# Installing Symfony

## Installing Symfony - Microservice

Install `skeleton`  if you only want a microservice:

`composer create-project symfony/skeleton <my_project>`

## Installing Symfony - Full Website

Install `website-skeleton` if you want to build a full website:

`composer create-project symfony/website-skeleton <my_project>`

`dhdresschers@ubuntu-vm:/var/www/localhost/wordpress$ sudo -u www-data composer create-project symfony/website-skeleton my_project`

# Composer

* see the whole list of Composer commands:

`dhdresschers@ubuntu-vm:/var/www/localhost$ composer list`

# Webserer

* Install Apache2

Run this command, where 'public' is the directory from where should be served:

`php -S 127.0.0.1:8000 -t public # 'public' is the forlder from where should be served`

# Folder structure

* bin - for unit tests
* config - config files
* public - public folder, the webserver looks for the index.php
* src - here the developer changes all the source files
* var - cache files
* vendor - folder for external php libraries

# Check Symfony requirements

`C:\wamp64\www\my_project>composer require symfony/requirements-checker`

Then check in the browser the 'check.php' file:

https://127.0.0.1:8080/my_project/public/check.php

# The '.env' file is the most important environment.

You have these settings:

`APP_ENV=dev`
`APP_ENV=prod`
`APP_ENV=test`

In the `config` - `packages` you see the following folders:

`dev`
`prod`
`test`

You see the 'bundles.php' file, if you add _dev, so it will be 'bundles_dev.php' than it will only apply to the 'dev' environment.

In the 'framework.yaml' file you see:

```
framework:
    secret: '%env(APP_SECRET)%'
```

Which means the secret is read from the '.env' file.

# Symfony Flex

[Symfony Recipes Server](https://flex.symfony.com/)

For the `symfony/twig-pack ` recipe you see 4 aliases:

* template
* templates
* twig
* twig-pack

If we want to install this, we use one of the aliases, in this case:
`

`C:\wamp64\www\my_project>composer require twig`

Now the package will be installed into the 'vendor' folder. This also creates a 'templates' folder where you use your template files.

# List all commands

`php bin/console`

# Install doctrine (database)

`composer require doctrine`

You will also see the databaseconnection in the .env file.










































































































