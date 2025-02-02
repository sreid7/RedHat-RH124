# RedHatLabs

**Access the command line**

1. Accessing the command line through windows using "putty" to ssh into the red hat box. 

2. From linux to linux using ssh <username@ip address> and entering a password from there.


**Manage files from the command line**

ls -l = list all files, whoami = (self - directory I am in), pwd = what directory I am in 

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

echo = inserting something into the file, ex. (echo "micheal is one" > micheal). This will insert this phrase into the micheal file

cat = display what is in the file ex. cat micheal = micheal is one

cp micheal /tmp (example, this will copy the file and place it into the tmp directory).

rm = remove files and directories, example (rm apoho), check to see if it is removed ls -ltr = list of files and directories to see if the files is gone

mv = rename and move files and directories (example, mv david putty, this renames the file). But also keeps the content. To move the file to another location use (mv putty /tmp)

mkdir = allows you to create a directory and the color of the directory will be blue lettering

rmdir = allows you to delete a directory 

- USE up or down arrow key to navigate past commands. (TIP)

 rm - Rf = forcefully removes subdirectories and its contents as well.

 Root = (su -) you must become root to have permission to do all functions on linux

 Exit Root = simply type "exit" will bring tyou back the normal user account.

 chgrp = change group to have access to a file or directory (ex. chgrp ricky reliable file)

 chown = change ownership and group at the same time (ex. chown falls:falls grimizod), this allows the owner and group to be changed at the same time.

 **Soft and Hard Links**


 inode = pointer or number of a file on a hard disk 

 soft link = link will be removed if file is removed or renamed

 hard = deleting renaming or moving the original file will not affect the hard link

 ln 

 ln -s

ls -ltri = The ls -ltri command in Linux combines multiple options for listing files in a directory with specific details. Here's what each flag means:

-l → Long format (shows file permissions, owner, size, modification time, etc.).
-t → Sorts files by modification time (newest first).
-r → Reverses the sorting order (oldest first instead of newest).
-i → Shows the inode number of each file (useful for identifying files uniquely within a filesystem).










