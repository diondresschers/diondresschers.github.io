# Apache 2 on Ubuntu 20.04

* Date: 2020-07-23
* By: Dion Dresschers
* License: CC BY-SA 4.0
* Version: 2020-07-23 15:28:00
* Inspired by: [Linux Foundation Cert Prep: HTTP Services (Ubuntu)](https://www.linkedin.com/learning/linux-foundation-cert-prep-http-services-ubuntu/welcome)

[LFCS: Online Courses, Training and Tutorials on LinkedIn Learning](https://www.linkedin.com/learning/search?entityType=COURSE&keywords=LFCS)

---

1. Install Apache on Ubuntu 20.04:
    * `apt install apache2`
1. Check which version of apache2 is installed:
    * `apache2 -v`
    * Result:
        ```
        Server version: Apache/2.4.41 (Ubuntu)
        Server built:   2020-04-13T17:19:17
        ```
1. Check the offical Apache2 documentation:
    * [Apache HTTP Server Version 2.4 Documentation - Apache HTTP Server Version 2.4](https://httpd.apache.org/docs/2.4/
1. See the section about VirtualHosts
    * [VirtualHost Examples - Apache HTTP Server Version 2.5](https://httpd.apache.org/docs/trunk/vhosts/examples.html)

## Apache 2 - See all the config files:
    * `tree \etc\apache2`

## Apache 2 - See all the special commands:

1. See all the special commands:
    * `a2<tab>`
1. This will result in:
    * `a2disconf  a2dismod   a2dissite  a2enconf   a2enmod    a2ensite   a2query`
1. See how to stop, start and restart apache2:
    * `man apache2ctl`
1. See all the options of apache2ctl: 
    * `sudo apache2ctl <tab>`
1. This will result in:
    ```
    configtest     fullstatus     graceful       graceful-stop  help           restart        start          status         stop   
    ```

## Apache 2 - Remove Apache2

1. Remove Apache2 with all config files. Stop apache2 first:
    * `apache2ctl`
1. Then:
    * `sudo apt-get --purge remove apache2`
    * `sudo apt-get remove apache2-common`
1. And check:
    * `whereis apache2`

## Apache2 - Check documentation

1. Check if the file exists:
    * `ls /usr/share/doc/apache2/README.Debian.gz`
1. Unzip the file:
    * `gunzip /usr/share/doc/apache2/README.Debian.gz`
1. Now you can read the unzipped file with `less`:
    * `less /usr/share/doc/apache2/README.Debian`

## Serving form /home/[user]

1. Enable the Apache2 module called `userdir`
    * `sudo a2enmod userdir`
1. Restart Apache2
    * `sudo systemctl restart apache2`
1. Check if the module is enabled:
    * `sudo a2query -m | grep userdir`
1. Then you can see the config file for the module `userdir`
    * `ls /etc/apache2/mods-available/ | grep userdir
1. This will result in:
    ```
    userdir.conf
    userdir.load
    ```
1. Change the value of the `userdir.conf` file, so it reflects to your own home directory:
    `sudo /etc/apache2/mods-available/userdir.conf`
1. So it reads:
    ```
    <IfModule mod_userdir.c>
            UserDir public_html
            UserDir disabled root

            <Directory /home/dion/public_html>
                    AllowOverride FileInfo AuthConfig Limit Indexes
                    Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
                    Require method GET POST OPTIONS
            </Directory>
    </IfModule>

    # vim: syntax=apache ts=4 sw=4 sts=4 sr noet    
    ```
1. By default the PHP Apache2 module won't let you allow serving from the users home directory.
1. If you open the `php.7.4.conf` file than you see some config how to make serving from a users home directory happen:
    * `less /etc/apache2/mods-available/php7.4.conf`
1. This shows:
    
    ```
    <FilesMatch ".+\.ph(ar|p|tml)$">
        SetHandler application/x-httpd-php
    </FilesMatch>
    <FilesMatch ".+\.phps$">
        SetHandler application/x-httpd-php-source
        # Deny access to raw php sources by default
        # To re-enable it's recommended to enable access to the files
        # only in specific virtual host or directory
        Require all denied
    </FilesMatch>
    # Deny access to files without filename (e.g. '.php')
    <FilesMatch "^\.ph(ar|p|ps|tml)$">
        Require all denied
    </FilesMatch>

    # Running PHP scripts in user directories is disabled by default
    # 
    # To re-enable PHP in user directories comment the following lines
    # (from <IfModule ...> to </IfModule>.) Do NOT set it to On as it
    # prevents .htaccess files from disabling it.
    <IfModule mod_userdir.c>
        <Directory /home/*/public_html>
            php_admin_flag engine Off
        </Directory>
    </IfModule>
    ```
1. Simply comment the line from `<IfModule ...> to </IfModule>` so it shows as suggested by the `php.7.4.conf` file, so it reads:

    ```
    #<IfModule mod_userdir.c>
    #    <Directory /home/*/public_html>
    #        php_admin_flag engine Off
    #    </Directory>
    #</IfModule>    
    ```
1. Make a `public_html` folder in your home directory:
    * `mkdir ~/public_html`    
1. Restart Apache2:
    * `systemctl restart apache2`
1. Now you can server your site from your home directory, for the user `dion` with:
    * `http://localhost/~dion`
