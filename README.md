# RedHat RH124

**Access the command line**

1. Accessing the command line through windows using "putty" to ssh into the red hat box. 

2. From linux to linux using ssh <username@ip address> and entering a password from there.


**Manage files from the command line**

ls -l = list all files, whoami = (self - directory I am in), pwd = what directory I am in 

ls -la = list all files and hidden files.

d = directory 

cd / = home 

cd .. = back climbing through directory

-------------------------

to create a file, you must first go into the home, example. "/home/srsoldier" , cd home, whoami, then cd into root, then touch (whatever file you want to create) 

touch jerry = creates a file

touch krammer = creates a file 

touch dion nelson kyle = creating three files at the same time

check to see if the file was created using ls -ltr to list all directories and files in alphabetical order based on time and reverse order (so the newest one on the bottom).

cp jerry clark = copies an existing file and naming it clark

vi = creates a file that can be edited. but do not write anything in it because it can be a problem to get out. Press SHIFT WQ! and ENTER to exit out. 

mkdir = making a directory 

**File Maintenenace Commands**

cp = copy a file and name it something

echo = inserting something into the file, ex. (echo "micheal is one" > micheal). This will insert this phrase into the micheal file. Use >> to insert more information into the file after creation.

cat = display what is in the file ex. cat micheal = micheal is one

cp micheal /tmp (example, this will copy the file and place it into the tmp directory).

rm = remove files and directories, example (rm apoho), check to see if it is removed ls -ltr = list of files and directories to see if the files is gone

mv = rename and move files and directories (example, mv david putty, this renames the file). But also keeps the content. To move the file to another location use (mv putty /tmp)

mkdir = allows you to create a directory and the color of the directory will be blue lettering

rmdir = allows you to delete a directory 

- USE up or down arrow key to navigate past commands. (TIP)

 rm - Rf = forcefully removes subdirectories and its contents as well.

 Root = (su -) you must become root to have permission to do all functions on linux

 Exit Root = simply type "exit" will bring you back the normal user account.

 chgrp = change group to have access to a file or directory (ex. chgrp ricky reliable file)

 chown = change ownership and group at the same time (ex. chown falls:falls grimizod), this allows the owner and group to be changed at the same time.

 **Soft and Hard Links**


 inode = pointer or number of a file on a hard disk 

 soft link = link will be removed if file is removed or renamed

 hard = deleting renaming or moving the original file will not affect the hard link

 ln (hard link)

 ln -s (soft link)

ls -ltri = The ls -ltri command in Linux combines multiple options for listing files in a directory with specific details. Here's what each flag means:

-l → Long format (shows file permissions, owner, size, modification time, etc.).
-t → Sorts files by modification time (newest first).
-r → Reverses the sorting order (oldest first instead of newest).
-i → Shows the inode number of each file (useful for identifying files uniquely within a filesystem).

ex. telnet localhost (error message can be sent to a file) ex. send to a file named "errorfile". Ex. telnet localhost 2> errorfile. 


**Input and Output Redirects**

ex. ls -la > micheal (content will be redirected into the micheal file)

one (>) will intially will create content, but will delete the content or overwrite the content when it is used a second time. To add additional content - a double greater sign (>>) must be used.

-----

ls -l /root 2> errorfile (this command routes the error which is classfied as 2 to a file called errorfile) - (Useful for automation)

RedHatVM ~]$ telnet localhost 2> errorfile
Install package 'telnet' to provide command 'telnet'? [N/y] y

 * Waiting in queue... 
 * Loading list of packages.... 
The following packages have to be installed:
 telnet-1:0.17-85.el9.x86_64	The client program for the Telnet remote login protocol
Proceed with changes? [N/y] y


 * Waiting in queue... 
 * Waiting for authentication... 
RedHatVM ~]$ cat errorfile
bash: telnet: command not found...
Failed to install packages: Failed to obtain authentication.
RedHatVM ~]$ 


**Pipe**

ex. cd /etc , then ls -ltr (creates a very long output of files and directories), then instead you can use ls -ltr | more, this displays the information by pages. You can tap the space bar to view each page.

to view the last line from the information of a command, (ls -l | tail -1)


**Help Commands**

1. whois (command)

2. (command) --help

3. man (command)


**Linux File Editor**


Continue Course with > udemy Linux File Editor - Red Hat Course

vi myfirstfile, then click ENTER.

click "i" for INSERT mode. Now the file can be edited. Type anything into the file. 

To save the file hit ESCAPE, and SHIFT Z Z. 

To see the file, use cat myfirstfile

To save the file a different way, type "vi myfirstfile" to get into the file. Type another word within the file and click "ESC, SHIFT (for :), wq! 

To delete a letter, type "x".

To replace a letter(s), type "r" on top of the letter you want to replace.

To delete an entire line, type "d".

To create a new line, type "o".

To undo deletion or any changes, type "u".

To search for a word whle not in the vi file, for example - type "grep lesson myfirstfile", to see the word lesson in the file. (This works when you are not currently inside the file - normal command.)

To search for a word while in the vi file, for example - type "/lesson". This will highlight a word within the vi file that you are looking for.

**Manage Local Users and Groups: User Account Management**

--Commands-- 

useradd, groupadd, userdel, groupdel, usermod

--Files--

/etc/passwd, /etc/group, /etc/shadow

Example:

useradd -g superheros -s /bin/bash -c "user description" -m -d /home/spiderman spiderman

Must login to "root", (type "su -" and enter password) to be able to configure users and groups.

useradd spiderman (created user)

Check user created, type (id spiderman), also to verify, go to home directory and type ls -l, to see if the user was created.

groupadd superheros

Check group, type "cat /etc/group"

Go delete user, type userdel -r spiderman, r means to remove the user's home directory and mail spool.

usermod -G superheros spiderman, -G adds the user spiderman to the superheros group (but replaces any existing secondary group memberships).

To check type, ex. grep spiderman /etc/group

useradd -g superheros -s /bin/bash -c "ironman" -m -d /home/ironman ironman (all parameters).

passwd ironman (to set passwords for users)

The /etc/login.defs File .The chage command -per user . Example: chage [-m mindays] [-M maxdays] [-d lastday] [-I inactive] [-E expiredate] [-W warndays] user

File = /etc/login.defs .PASS_MAX_DAYS 99999 . PASS_MIN_DAYS 0 . PASS_MIN_LEN 5 . PASS_WARN_AGE 7 (For all users)

ex. chage -m 5 -M 90 -W 10 -I 3 babubutt (For individual users)

To switch users: su - "username", (then enter password for the user), sudo (if can't become root), visudo (edits user permissions file: /etc/sudoers)

In the visudo file, by default the wheel group has root permission to run commands. A user can be added to the wheel group by using the usermod command. 

Ex. usermod aG- wheel sreid7

Testing sudo. Ex. sudo dmidecode and enter password (this command should display system data)

Testing sudo. Ex. sudo fdisk -l (this command should display the size of the disk)

**File Permissions**

There are 3 types of permissions (r = read, w = write, and x = execute)

-rwxrwxrwx (First three letters are for the user, second three are for the group, and the last three letters are for everyone that has access to the system).

ls -l will display all permissions 

chmod = this is the command to make changes to the permissions.

Ex. ls -l jerry (to display a specific file and permissions)

Ex. chmod g-w jerry (will remove write permission from the group level)

Ex. chmod a-r jerry (will remove the permission from all user to read the jerry file)

Ex. chmod u-w jerry (will remove the permission for the logged in user to write on the file)

Ex. chmod u+rw jerry (will give permission to the logged in user to read and write the file)

Ex. chmod g+rw jerry (will give group permission to read and write the file)


**14:43 User Account**

**File permissions Lab - 10:32 Udemy





 
