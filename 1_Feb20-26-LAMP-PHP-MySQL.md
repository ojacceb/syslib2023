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

Created sql user

Created database

learned some commands for mysql
- \h = help
- \c = clear current input statement. You can use this if you've typed something incorrectly and need to start over. 
- \q = quit mysql
- control l (as in llama) = clear screen
- update database = edit existing database
- insert database = add new database


Also learned how to log in as opac user
```
$mysql -u opacuser -p
```
it then prompts for password and you enter the user's password. 


***Side Notes/Issues/New Knowledge***

-On 2/25 when I opened my computer's commandline, it said my google cloud software needed an update. I ran that update using the command provided. For some reason it errored out part way through the update process. I tried then to proceed with logging into my virtual machine however something had been deleted from my gcloud software and I wasn't able to log in. I noticed that my machine had started to retry the update command but I had interrupted it on accident. So I re-ran the command and it was successful that time. After it completed the updates I was able to login to the virtual machine as normal. 

-On 2/25 after completing the updates to my gcloud software, my virtual machine prompted me to reboot.  
I googled how to reboot a virtual machine and found [this website](https://www.cs.stonybrook.edu/about-us/csintranet/faqs/Ubuntushutdown)
I used the `sudo reboot` command and my virtual machine disconnected. 
When I ran the command from my machine to log in again the promt to reboot was gone. 

-On 2/25 I figured out how to delete the repo that I had accidentally cloned from Dr. Burns's GitHub during the GitHub week.  
Previously I tried to run the `rm` command, but received the error that it wouldn't work because it was a directory.
When I looked at the man page for the `rm` command it was supposed to work for directories so I was confused. For several days I just gave up after that point.
Today I relized it was actually not a director, but a git repo. So I googled how to delete a git repo. 
I found [this website](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/delete-local-git-repository-repo-command-windows-linux-rm#:~:text=Command%20line%20Git%20repository%20delete&text=Just%20run%20the%20rm%20command,and%20folder%20to%20remain%20untouched.)
It suggested running `rm -f -r repo name`.
When I ran that command the repo was successfully deleted!! 


