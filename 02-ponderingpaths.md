# 1- the root
we can use cd / to go to the root directory

# 2- programme and absolute paths
accessing absolute path using /challenge/run

# 3- position the self
i went to challenge in the current directory </br>
it said you are not in 'etc' </br>
so i accessed etc then /challenge/run</br>
the final solution was in the etc directory</br>

# 4- position elsewhere

`hacker@paths~position-elsewhere:/home$ /challenge/run`
`Incorrect...`

`You are not currently in the /usr/aarch64-linux-gnu/include/gnu directory.`</br>
`Please use the cd utility to change directory appropriately.`</br>
`hacker@paths~position-elsewhere:/home$ /usr/aarch64-linux-gnu/include/gnu/challenge/run`</br>
`bash:/usr/aarch64-linux-gnu/include/gnu/challenge/run: No such file or directory`
`hacker@paths~position-elsewhere:/home$ /usr/aarch64-linux-gnu/include/gnu/challenge/run`</br>
`bash: /usr/aarch64-linux-gnu/include/gnu/challenge/run: No such file or directory`</br>
`hacker@paths~position-elsewhere:/home$ cd /usr/aarch64-linux-gnu/include/gnu`</br>
`hacker@paths~position-elsewhere:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run`</br>
`Correct!!!`

same to previous on accesing the challenge file it said the location of the place where file was located so i accessed it from there 

# 5- position yet elsewhere

same process as above </br>
the file was not at challenge in the current directory</br>
the location was mentioned to access the file finally  using `/challenge/run`

# 6- in=mplicit relative paths from /

after accessing th / </br>
not using / as its relative path we use -> challenge/run</br>
for the solution

# 7-Implicit Relative Path
Navigate to root (/) and run challenge/run from the current directory to get the flag.

# 8-Explicit Relative Path
Running `./challenge/run `from root works the same as `challenge/run`.

# 9-Explicit Current Directory
Go to `/challenge` and run `./run` to get the flag.

# 10-Home Directory
Use `~/a` as the argument for `/challenge/run` to meet the requirements and get the flag.
