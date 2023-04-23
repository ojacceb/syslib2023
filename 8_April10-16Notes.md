# Notes April 10-16

- Supposed to use this command to install Koha repository
`echo 'deb http://debian.koha-community.org/koha stable main' | sudo tee /etc/apt/sources.list.d/koha.list`
- Did not get the “OK” message that Dr. Burns got. Instead it echoed back the first part of the command. When I tried to proceed to the next step and run `apt update` some things related to koha seemed to update, but there was also an error stating public keys for some things weren’t available. 
1. I asked Chat GPT what the command that was erroring out meant (I didn’t really understand what it was doing). 
2. This was Chat GPT’s answer:
> This Linux command adds a new software repository to the system's package manager by creating a file called `koha.list` in the `/etc/apt/sources.list.d/` directory and adding a specific line to it.
> The `echo` command is used to print the string `deb http://debian.koha-community.org/koha stable main` to the standard output stream. The vertical bar or pipe character `|` takes the output of the previous command and redirects it as input to the next command.
> The `sudo tee` command is used to write the output of the `echo` command to a file called `koha.list` in the `/etc/apt/sources.list.d/` directory. The `sudo` command is used to execute the `tee` command with administrative or superuser privileges, which are required to modify system files.
> In summary, the command adds a new software repository for Koha, a free and open-source integrated library system, to the system's package manager.
3. I exited the root user using the command `exit`
4. I want to see if I can find the directory that the command was trying to modify to see if it did it?
5. I wonder if the problem is that the command has `sudo` in it, but I’m logged in as root so the `sudo` shouldn’t be necessary, right?
6. I asked Chat GPT what the error messages meant and this was it’s response below. It confirmed my hypothesis that the public key for the koha repository was missing which is what caused the errors.
> This is the output of running the `apt update` command in the Linux command line, which updates the package lists for the system's package manager. The output shows that the update process was successful for the Ubuntu repositories (http://us-central1.gce.archive.ubuntu.com), but there was an error with the Koha repository (http://debian.koha-community.org/koha). 
> The error message states that the public key for the Koha repository is not available, which means that the package manager cannot verify the authenticity of the packages from this repository. As a security measure, the package manager has disabled updates from this repository by default.
> The next command, `apt show koha-common`, is used to display information about the package koha-common. However, the output shows that the package could not be located, indicating that it is not available in any of the enabled repositories.
> To resolve this issue, you can try importing the missing public key for the Koha repository using the `apt-key` command, or contact the maintainers of the Koha repository for assistance.
7. I asked Chat GPT how to use the `apt-key` command to download a key and this is the response it gave:
>You can use the `apt-key` command to download and add the missing public key for the Koha repository to your system. Here are the steps to do so:
> 1. Find the key ID for the missing public key. In your case, the error message shows that the key ID is `3C9356BBA2E41F10`.
> 2. Download the key from a key server using the `apt-key adv` command. For example, to download the key from the Ubuntu key server, you can run the following command:
>`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3C9356BBA2E41F10`
> 3. Update the package lists using the `apt update` command to refresh the package manager's cache and enable updates from the Koha repository.
> After completing these steps, you should be able to update packages from the Koha repository without encountering the missing public key error.

8. I followed the instructions, we downloaded a key. Then I ran `sudo apt update` as Chat GPT instructed and it didn’t throw any errors this time like it did previously when it threw the key error.
9. I switched back to root user `sudo su` and ran the `apt show koha-common` command again and it worked just like it showed on the video!
10. Opening the web app version of Koha went smoothly and I was able to complete the assignment.

## However

Next day: After posting about my problem-solving in Element, Dr. Burns pointed out a command that I had accidentally skipped over which was supposed to provide the security keys needed.  It was clear in the written instructions, I just skipped over it.  

### Lessons Learned
- Always re-read instructions (if available) when you are stuck!
- Be patient and take time to problem solve, even if it feels like you’re in a hurry.
- I do think that using Chat GPT was helpful, because it did clarify that I was understanding the commands I was up to that point in the instructions, and I understood the error I got.  So that was helpful and reassuring.  It might have been better to do a little more specific googling in the documentation about Koha before blindly using the Chat GPT command. Or waiting until other members of my class had time to respond to my question. 
- That being said, if I had been on my own it seems to have resolved the issue and moved me along. I also did understand what the issue was, I just didn’t have the programming skills to move to the problem-solving step on my own. So Chat GPT filled that gap. 

 

