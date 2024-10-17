#Perciving Permissions

## 1-Changing File Ownership

The two most important user accounts are:

-Your user account! On pwn.college, this is the hacker user, regardless of what your username is.
-root. This is the administrative account and, in most security situations, the ultimate prize. If you take over the root user, you've almost certainly achieved your hacking objective!

`hacker@dojo:~$ ls -l /flag`<br>
`-r-------- 1 root root 53 Jul  4 04:47 /flag`<br>
`hacker@dojo:~$ cat /flag`<br>
`cat: /flag: Permission denied`<br>
`hacker@dojo:~$`<br>

Here, you can see that the flag is owned by the root user (the first root in that line) and the root group (the second root in that line).

Interestingly, we can change the ownership of files! This is done via the chown (change owner) command:

chown [username] [file]

Typically, chown can only be invoked by the root user. Let's pretend that we're root again (that never gets old!), and watch a typical use of chown

`-rw-r--r-- 1 root root    0 May 22 13:42 college_file`<br>
`drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory`<br>
`root@dojo:~# chown hacker college_file`<br>
`root@dojo:~# ls -l`<br>
`total 4`<br>
`-rw-r--r-- 1 hacker root    0 May 22 13:42 college_file`<br>
`drwxr-xr-x 2 root   root 4096 May 22 13:42 pwn_directory`<br>

college_file's owner has been changed to the hacker user, and how hacker can do with it whatever root had been able to do with it! If this was the /flag file, that means that the hacker user would be able to read it!

Solution- 
`/challenge/run`
`chown hacker /flag`
`ls -l`
`cat /flag`

## 2- Groups and Files
You can check what groups you are part of with the id command

graphical output can be done via the special /dev/fb0 file

group ownership can be changed with the `chgrp` (change group) command! Unless you have write access to the file and membership in the new group, this typically requires root access,

Solution-
`ls -l`<br>
`chgrp hacker /flag`<br>
`cat /flag`<br>

## 3- Fun with group names
Solution-
`id`<br>  *it gave the information about the current group i am in *
`ls -l`<br>
`chgrp grp23713 /flag`<br>
`cat /flag`<br>

## 4- Changing Permissions

-rw-r--r-- 1 hacker hacker    0 May 22 13:42 college_file<br>
drwxr-xr-x 2 hacker hacker 4096 May 22 13:42 pwn_directory<br>

the first character there is the file type. The next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting permissions for the owning user, 3 characters denoting the permissions for the owning group, and 3 characters denoting the permissions that all other access

Each character of the three represent permission for a different type:

- r - user/group/other can read the file (or list the directory)
- w - user/group/other can modify the files (or create/delete files in the directory)
- x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
- - - nothing 

For college_file above, the rw-r--r-- permissions entry decodes to:

- r: the user that owns the file (user hacker) can read it
- w: the user that owns the file (user hacker) can write to it
- `-`: the user that owns the file (user hacker) cannot execute it
- r: users in the group that owns the file (group hacker) can read it
- `-`: users in the group that owns the file (group hacker) cannot write to it
- `-`: users in the group that owns the file (group hacker) cannot execute it
- r: all other users can read it
- `-`: all other users cannot write to it
- `-`: all other users cannot execute it

 Like ownership, file permissions can also be changed. This is done with the chmod (change mode) command. The basic usage for chmod is:

`chmod [OPTIONS] MODE FILE`

You can specify the MODE in two ways: as a modification of the existing permissions mode, or as a completely new mode to overwrite the old one.

In this level, we will cover the former: modifying an existing mode. chmod allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute. For example, to add read access for the owning user, you would specify a mode of u+r. write and execute access for the group and the other (or all the modes) are specified the same way. More examples:

- `u+r`, as above, adds read access to the user's permissions
- `g+wx` adds write and execute access to the group's permissions
- `o-w` removes write access for other users
- `a-rwx` removes all permissions for the user, group, and world
Solution - in this question i dont have the permission to change the ownership or group but i can change the permission to read the flag

`chmode o+r /flag`<br>
`cat /flag`<br>

## 5- Executable Files
When you invoke a program, such as /challenge/run, Linux will only actually execute it if you have execute-access to the program file

Solution -
-hacker@permissions~executable-files:/$ cd
-hacker@permissions~executable-files:~$ /challenge/run
-bash: /challenge/run: Permission denied
-hacker@permissions~executable-files:~$ chmod o+x /challenge/run
-hacker@permissions~executable-files:~$ /challenge/run
-bash: /challenge/run: Permission denied
-hacker@permissions~executable-files:~$ cd /challenge/run
-bash: cd: /challenge/run: Not a directory
-hacker@permissions~executable-files:~$ cd /challenge
-hacker@permissions~executable-files:/challenge$ ./run
-bash: ./run: Permission denied
-hacker@permissions~executable-files:/challenge$ chmod o+x ./run
-hacker@permissions~executable-files:/challenge$ ./run
-bash: ./run: Permission denied
-hacker@permissions~executable-files:/challenge$ chmod u+x ./run
-hacker@permissions~executable-files:/challenge$ ./run
-Successful execution! Here is your flag:
-pwn.college{kib-SbIEzdB0flpEwgG3tktFUHU.dJTM2QDLzQTO0czW}

## 6- Permission Tweaking Practise

On following the user instructions we get the flag
