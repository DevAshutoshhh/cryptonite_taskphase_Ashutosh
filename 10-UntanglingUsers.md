## 1- Becoming Root With su

su (the switch user command). This is not typically used to elevate to root access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

su is a setuid binary:

`hacker@dojo:~$ ls -l /usr/bin/su`<br>
`-rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/su`<br>

Because it has the SUID bit set, su runs as root. Running as root, it can start a root shell! Of course, su is discerning: before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password:

`hacker@dojo:~$ su`<br>
`Password: `<br>
`su: Authentication failure`<br>

This check against the root password is what obsoletes su. Modern systems very rarely have root passwords, and different mechanisms (that we will learn later) are used to grant administrative access

Solution-
`hacker@users~becoming-root-with-su:/home$ /challenge/getroot`<br>
`bash: /challenge/getroot: No such file or directory`<br>
`hacker@users~becoming-root-with-su:/home$ su`<br>
`Password:` <br>
`root@users~becoming-root-with-su:/home# cat /flag`<br>
`pwn.college{cOxBmZxjRr734nlQ09fxPXn2Fel.dVTN0UDLzQTO0czW}`<br>

## 2- Other Users With su

With no arguments, su will start a root shell (after authenticating with root's password). However, you can also give a username as an argument to switch to that user instead of root.

For exmaple we can see the solution
Solution-
`hacker@users~other-users-with-su:/home$ su zardus `<br>
`Password: `<br>
`zardus@users~other-users-with-su:/home$ /challenge/run`<br>
`Congratulations, you have become Zardus! Here is your flag:`<br>
`pwn.college{Y69ZU7hbTogC21zL447RLAtKM1u.dZTN0UDLzQTO0czW}`<br>

## 3- Cracking Passwords

Solution - 

`hacker@users~cracking-passwords:/home$ /challenge/shadow-leak`<br>
`bash: /challenge/shadow-leak: Permission denied`<br>
`hacker@users~cracking-passwords:/home$ cd`<br>
`hacker@users~cracking-passwords:~$ /challenge/shadow-leak`<br>
`bash: /challenge/shadow-leak: Permission denied`<br>
`hacker@users~cracking-passwords:~$ ./challenge/shadow-leak`<br>
`bash: ./challenge/shadow-leak: No such file or directory`<br>
`hacker@users~cracking-passwords:~$ john /challenge/shadow-leak`<br>
`Created directory: /home/hacker/.john`<br>
`Loaded 1 password hash (crypt, generic crypt(3) [?/64])`<br>
`Press 'q' or Ctrl-C to abort, almost any other key for status`<br>
`aardvark         (zardus)`<br>
`1g 0:00:00:20 100% 2/3 0.04962g/s 288.9p/s 288.9c/s 288.9C/s Johnson..buzz`<br>
`Use the "--show" option to display all of the cracked passwords reliably`<br>
`Session completed`<br>
`hacker@users~cracking-passwords:~$ su zardus`<br> 

## 4- Using SUDO

`hacker@users~using-sudo:/home$ /challenge/flag`<br>
`bash: /challenge/flag: No such file or directory`<br>
`hacker@users~using-sudo:/home$ sudo cat /flag`<br>
`pwn.college{MLnp3-skquJSJuQajmI5XD6_F8e.dhTN0UDLzQTO0czW}`

