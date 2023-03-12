# Notes from the week of March 6-12

## New program: tmux
### Allows you to have several "panes" (think tabs) open in the same commandline window
#### Key Commands:
- `ctrl+b` `shift+%` = split pane view with horizontal layout
- `ctrl+b q` = shows pane numbers
- `ctrl+b` `q 0(zero)-9` = switch to typing in that number pane. 
- `ctrl+b x` = close current pane
- `ctrl+b` `shift+&` = close current window

## Tasks from Assignment this week:

- create an index.html file in a new cataloging directory in /var/www/html
- create an insert.php file in the new cataloging directory
	- Don't forget to change the fake IP address to the VM pulbic IP address for the return links to work
	- test by finding public ip address of VM and navigating to ip address/cataloging
	- it worked!
- secure your cataloging directory with the htpasswd command
	- Used the same username and pw as Dr. Burns in the video
- add some additional records using the new web form
	- It's much easier to add records using the website interface as opposed to directly typing into the mySQL
- use your OPAC to retrieve the new records
	- website for the record retrevial page is *IP Address*  + /opacbb.html


## Journaling:
- No particular problems this week. 
- I forgot to chagne the IP address initially in the PHP file to make the return hyperlink work
- I was able to find that spot in the file 'sudo nano *filename*' and correct it
- It's definitely easier to use the OPAC web interface than using mySQL directly but I find it much more interesting to try to figure out mySQL
- I loved having two panes open in tmux! Haveing my notes pane and my terminal open at the same time made it easier for me to focus on the tasks. 




