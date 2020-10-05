<img src="../static/amsterdam_umc_logo_rgb.svg" height="50%" width="50%" style="display: block; margin-left: auto;
 margin-right: auto; width: 50%;">
<p style="text-align:center; font-size: 200%;">Apotheek</p>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fork-awesome@1.1.7/css/fork-awesome.min.css" integrity="sha256-gsmEoJAws/Kd3CjuOQzLie5Q3yshhvmo7YNtBG7aaEY=" crossorigin="anonymous">

* License: <i class="fa fa-creative-commons" aria-hidden="true"></i> CC BY-SA 4.0
* Intitially by: Daniel Weibel - Downloaded 2020-03-16 [MySQL Cheatsheet](https://dresschersd.net/misc/mysql-cheatsheet.html)
* Adapted by: Dion Dresschers of Amsterdam UMC
* Version: 2020-03-16 11:23:31

# MySQL Cheat Sheet

## Install on Ubuntu 18.04
kee
```
$ sudo apt install mysql-server
```

## Access mysql

```
$ sudo mysql
```

## Create a user

```
mysql> CREATE USER 'user'@'%' IDENTIFIED BY 'password';
```

```
mysql> create user 'dresschers'@'localhost' identified by 'password';
```

## Give read only access to a database

```
GRANT SELECT ON db.* TO 'user'@'%';
FLUSH PRIVILEGES; # To make the change direct
```
## Login

```
$ mysql -u dresschers -p         # Log in as 'dresschers' with password prompt
$ mysql -u dresschers -pdion     # Log in as 'dresschers' with password 'dion'
$ mysql -u dresschers -pdion db  # Log in and select database 'db'
```

## Exit MySQL

```
mysql> exit
```

## List users

```
mysql> select User,Host from mysql.user;
```


## List databases that are accessible for current user

```
mysql> show databases;
```

## Change to a specific database

```
mysql> use db_name;
```

## Show all tables in the current database

```
mysql> show tables;
```

## Select 10 rows

```
mysql> select * from tbl_name limit 10;
```

## Delete all rows from a table

```
mysql> delete from tbl_name;
```

## Show column data types

```
mysql> show columns from tbl_name;
```

## Count number of columns in table

```
mysql> select count(*)
       from information_schema.columns
       where table_name='tbl_name';
```

## Create a new database (login to MySQL as root)

```
mysql> create database new_db;
```

## Create table in new DB with schema of a table in an existing DB

```
mysql> create table new_db.tbl_name like old_db.tbl_name;
```

## Create a table by defining all the columns manually

```
mysql> create table connected_devices (
         ap_id                 int,
         device_mac            char,
         timestamp             timestamp,
         interface             varchar(255)
       );
```

## Grant full DB access to another user

```
mysql> grant all on new_db.* to 'username'@'host'
```

## Load data from a CSV file into a table

```
$ mysql --local-infile -u dresschers -p  # Start MySQL with 'local infile' enabled
```

```
mysql> load data local infile 'file.csv' into table tbl_name
       fields terminated by ',' enclosed by '"';
```
