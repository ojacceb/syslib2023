# notes from the week of Feb. 20-26. LIS 690

## this week we learned to install and configure a LAMP stack (Apache, PHP and MySQL)

***Purpose***
LAMP = Linux, Apache, MySQL, PHP
PHP = scripting language
MySQL = relational database


***Task***
Install Apache: 

1. first read [getting started] (https://httpd.apache.org/docs/2.4/getting-started.html) page on Apache website. 
- useful to read regularly 

1. upgrade systems first

```
sudo apt update
sudo apt -y upgrade
```
1. `apt show apache2` shows information about the program, but isn't super useful as it may show too much information to be useful especially with big programs.

1. to install: `sudo apt install apache2`

1. stopped first video at 23:13. installed apache2, created first basic web page

