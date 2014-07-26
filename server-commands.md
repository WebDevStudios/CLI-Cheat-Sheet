Server Commands
====

One big advantage of the command line is the ability to manage remote servers easily. Most web servers do not have a visual desktop to access, and while many have built in control panels, you can have greater control by connecting to them through the command line.

There are several distrobutions of Linux, this cheat-sheet will focus on Ubuntu.

Connecting
----

`ssh` (secure shell) allows you to connect to a remote server using the command line. The standard usage is `ssh username@server-address.net` where username is your username on the remote server amd server-address.net is the URL or IP of the remove server.

SSH has many powerful features, such as unique keys per remote server you connect to (more secure) and the ability to set default configuration on a per server basis. Read the [SSH Management](ssh-management.md) page to learn how to take full control over your SSH connections.

Package Management
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
