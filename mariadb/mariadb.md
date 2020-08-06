# MariaDB on Ubuntu 20.04

* Date: 2020-07-26
* By: uOnline.nl & Dion Dresschers
* License: CC BY-SA 4.0
* Version: 2020-07-26 11:37:56
* Inspired by: [Installing Apache, MySQL, and PHP](https://www.linkedin.com/learning/installing-apache-mysql-and-php-3/install-mysql-on-ubuntu-linux)

---

1. Install MariaDB
    * `sudo apt install mysql-server`
1. Then run 'mysql_secure_installation - improve MariaDB installation security`'
    * `sudo mysql_secure_installation`
1. Enter a password (minimal 8 characters)
1. Then enter all the defaults by using the `Enter`-key
1. Then turn on password authentication (this is disabled by default):
    * `sudo mysql`
1. This will result in:
    ```
    Welcome to the MariaDB monitor.  Commands end with ; or \g.
    Your MariaDB connection id is 56
    Server version: 10.3.22-MariaDB-1ubuntu1 Ubuntu 20.04

    Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

    MariaDB [(none)]> 
    ```
1. Then show all databases:
    * `show databases`
1. This will result in:
    ```
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | mysql              |
    | performance_schema |
    +--------------------+
    3 rows in set (0.000 sec)    
    ```
1. Then use the database `mysql`:
    * `select mysql`
1. Then you can see all tables:
    * `show tables`
1. Then select all rows from `users`
    * `select * from user;
1. Then select only the `user` and `authentication_string;`
    * `select user, authentication_string from user;`
    * or
    * `select user, authentication_string from mysql.user;`
1. This results in:
    ```
    +------+-----------------------+
    | user | authentication_string |
    +------+-----------------------+
    | root |                       |
    +------+-----------------------+
    ```
1. This does not work:
1. Set a username for the user `root` so you don't have to use `sudo mysql`:
    * `alter user root'@'localhost identified by '<password>';
1. Restart mysql:
    * `sudo systemctl restart mysql`
1. Log in via the `root`-MySQL user, don't start it as the `root` Linux user:
    * `mysql -u root -p`

## Install MySQL Workbench

1. Go to your home folder:
    `cd ~`
1. Make a temporary folder:
    `mkdir temp`
1. Go into that directory:
    `cd temp`
1. Download the installation file:
    `wget https://dev.mysql.com/get/mysql-apt-config_0.8.15-1_all.deb`
1. Install the file and keep entering it.
    `sudo dpkg -i mysql-apt-config*.deb`
1. Run the system update command
    * `sudo apt update`
1. Install MySQL Workbench:
    * `sudo apt install mysql-workbench-community`    
1. Start MySQL Workbench    
    * `mysql-workbench &`