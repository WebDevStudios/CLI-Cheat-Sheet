Server Commands
====

There are several distrobutions of Linux, this cheat-sheet will focus on Ubuntu.

Package Managment
----

`sudo apt-get update`

or

`sudo apt-get update && sudo apt-get upgrade`

LAMP Stack
----

This command will install the entire stack: `sudo apt-get install lamp-server^`

Or you can install them one-by-one:

> * Apache `sudo apt-get install apache2 libapache2-mod-php5`

rather use NGINX?

> * NGINX `sudo apt-get install nginx`

> * MySQL `sudo apt-get install php mysql-server mysql-client`
> * PHP `sudo apt-get install php5 php5-gd php5-mysql php5-curl php5-cli php5-cgi php5-dev php5-fpm`
> * phpMyAdmin `sudo apt-get install phpmyadmin`
