#Notes: Week of feb 27-mar 5#

##Problem 1:##
-When I logged in to my VM it says that there is a system restart required. 
-Googled "Google VM "system restart required"" and found [this website](https://askubuntu.com/questions/258297/should-i-always-restart-the-system-when-i-see-system-restart-required)
-suggested the command `sudo reboot` from the commandline. 
-I ran that and my VM shut down as expected
-My commandline then gave me a prompt to install updates to the Google Cloud CLI components by running `gcloud components update`
-The command installed some updates and then I logged in to my VM again. 

---
##Journal assignment: Document the processes and technologies that we use this week in your own words## 
My OPAC website:(http://34.123.153.94/opacbb.html)

-We are creating a search page with a PHP-powered script that allows us to search the records in our mini database.
-The new html and php files that we create will need to be saved in the **/var/www/html** directory in order to be run as part of the web page!! 
-`cd /var/www/html` to get there. 
-`sudo nano opacbb.html` to create a new html file and copy the code from Dr. Burns over
-change the placeholder ip address to my VM public ip address.
-create new php search script file with the code from Dr. Burns (copied from Chat GPT with some modifications)
-`sudo nano search.php`
-change placeholder ip address to my VM ip address. 

-web address for my search page: (http://34.123.153.94/opacbb.html)

##For practice working in mySQL##
1. Login: `mysql -u opacuser -p` use the password saved in the login.php file. 
(you can cat the file using the command `sudo cat login.php` to reference username and password info)
2. Use the `insert` command to add new record to the DB.
**example:**
```
insert into books
(author, title, publisher, copyright) values
('Emma Donoghue', 'Room', 'Little, Brown \& Company', '2010-08-06'),
('Zadie Smith', 'White Teeth', 'Hamish Hamilton', '2000-01-27');
```
##problem 2: ran above code and received the error "Error 1046 (3D000): No database selected##
-Googling how to see existing databases in mySQL (looking for something similar to the ls command on the linux commandline). 
-*Later saw that Dr. Burns posted about a way to modify a bash file so that mySQL always shows what database you are in*

##New mySQL commands:##
- SHOW TABLES- Lists all tables (but you have to have already selected a DB)
- SHOW DATABASES - Lists all DBs
- USE ______ - to open database that you want to use (e.g. USE opacdb)
- CREATE TABLE _____ - create table with the name of the table in the space and other parameters defined. 
example:
```
create table ____(
id int unsigned not null auto_increment,
author varchar(150) not null,
title varchar(150) not null,
copyright date not null,
primary key (id)
);
```
-SHOW TABLES - lists out the tables in the db. 
- DESCRIBE _____ = blank is the name of the table. Command lists out the parameters of the table and the fields. 
- SELECT = selects specific records from table using search parameters.  To see whole table use `select * from books;`


-[From the website](https://dev.mysql.com/doc/refman/8.0/en/creating-database.html)
Creating a database does not select it for use; you must do that explicitly. To make menagerie the current database, use this statement:
```
mysql> USE menagerie
Database changed
```
Your database needs to be created only once, but you must select it for use each time you begin a mysql session. You can do this by issuing a USE statement as shown in the example. Alternatively, you can select the database on the command line when you invoke mysql. Just specify its name after any connection parameters that you might need to provide. For example:
```
$> mysql -u opacuser -p opacdb
Enter password: ********
```

>in that code 
>-u=username
>-p=prompt to enter the password
>opacdb=the name of whatever database you want to work in after you log in.


##Problem 3##
-I somehow created an incomplete command entry in mySQL and the beginning of my line chagned to "'>" instead of "->"
-[This website told me how to fix it](https://stackoverflow.com/questions/17538549/what-does-the-symbol-mean-in-the-command-line-in-mysql)

##Conclusion##
-Successfully created some files in directories based on stuff we learned in previous weeks
-Learned several more mySQL commands and the key piece of information that you are not automatically in any database when you log in
-Successfully used google, TLDR and documentation on stackoverflow to trouble shoot several problems. 
