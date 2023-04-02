# Notes for LIS 690 week of March 27-April 2

## Objectives this week: install Omeka

Instruction 1. Create a new user and a new database in MySQL for the Omeka installation (do not re-use the WordPress database, user, or credentials).
1. change to root user - `sudo su`
1. change to root mysql use: `mysql -u root`
1. create new user for omeka w/in sql  user sql command: `create user 'newusername'@'localhost' identified by 'insertpassword';`
1. create new database for omeka mysql syntax: `create database databasename;`
1. grant privileges to the new user for the database mysql syntax: `grant all privileges on databasename.* to 'username'@'localhost';`
1. mysql command `show databases;` to see database list and confirm success!
1. quit mysql `\q`

1. exit root user w/ command `exit`

Instruction 2: "Use `wget` from your server to download Omeka Classic as a zip file and extract it in `/var/www/html`
1. change to the correct directory `cd /var/www/html`
1. use wget to get download the zip file containing Omeka Classic `sudo wget https://github.com/omeka/Omeka/releases/download/v3.1/omeka-3.1.zip`
1. `ls` to confirm download - success! the omeka-3.1.zip directory is saved in the /var/www/html directory!
1. install unzip with the apt command `sudo apt install unzip`
1. unzip successfully installed. `tldr unzip` says that the command to unzip a directory into the current directory is `unzip filepath`
	you need to sudo the unzip command on my machine.
1. Rename the unzipped omeka-3.1 directory to omeka `sudo mv omeka-3.1 omeka`

Instruction 3: In the extracted directory, find the db.ini file and add your database credentials, and replace all values containing XXXXXX, with the appropriate information. This is the same thing we did with the login.php file for our bare bones OPAC/ILS and the wp-config.php file for WordPress.
1. `cd omeka` to open the new directory. 
1. `sudo nano db.ini` to open the file we need to edit. 
My config file:
Host = "localhost"
Username = "omeka" (I set that up in mysql in an earlier step)
password = "XXXXXX" (I entered the one I set up in mysql in an earlier step)
dbname = "omeka" (I set that up in mysql in an earlier step)
prefix = "omeka_" (this was prefilled in the config file)
charset = "utf8" (this was prefilled in the config file)
;port = "" (this was blank in the config file and I didn't know what info to add so I left it blank!)
I wasn't sure what to use for the "host" but I googled it and found this page on the Omeka Classic technical site https://omeka.org/classic/docs/Technical/DatabaseConfigurationFile/

Instruction 4: Use the chown command like we did with WordPress on the files directory in the omeka directory. The user and owner should again be www-data.
1. I found this instruction from the wordpress install instructions: `sudo chown -R www-data:www-data *` and ran it. it seemed to work but I don't know how to verify. I guess I'll see when I try to add content to the omeka.

Instruction 5: Restart Apache2 and MySQL
1. 'sudo systemctl restart apache2'
1. 'sudo systemctl restart mysql' 
(from the Instal PHP and MySQL instructions 5.3 in the handbook)

Instruction 6: In your web browser, go to http://your-ip-address/omeka/ and complete the setup via the web form, just like you did with WordPress.
1. Went to the webpage and it worked!
1. set up the stuff, I left the default in the photo fields, didn't fill in the tag delimiter or the copyright information but it seemed to work OK. When I clicked submit and selected the option for the public website it opened a webpage. Now I need to figure out how to add things. 

Instruction 7: Add some content to the Omeka.
 1. adding content using the online interface is clear and self-explanatory. So far so good!


