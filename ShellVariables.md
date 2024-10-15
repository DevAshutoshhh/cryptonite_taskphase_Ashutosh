# 1- Printing Variables
To print we use `echo` and to print any variable we prepend variable with `$`.<br>
Solution - $FLAG

# 2- Setting Variables
To assign a value to a variable we use `variable=value` no GAP.<br>
Solution - PWN=1337

# 3- Multi-word Variables
If we need spaces in between the names we need to keep it as `variable="val1 val2"`<br>
Solution - PWN="hello world"

# 4- Exporting Variables
By default, variables that you set in a shell session are local to that shell process. That is, other commands you run won't inherit them. You can experiment with this by simply invoking another shell process in your own shell.<br><br>

`sh` creates a new shell without affecting the present shell.<br>
EXAMPLE -<br><br>

`hacker@dojo:~$ VAR=1337<br>`
`hacker@dojo:~$ echo "VAR is: $VAR"<br>`
`VAR is: 1337`<br>
`hacker@dojo:~$ sh`<br>
`$ echo "VAR is: $VAR"`<br>
`VAR is: `<br>

When you export your variables, they are passed into the environment variables of child processes.<br><br>

`hacker@dojo:~$ VAR=133`<br>
`hacker@dojo:~$ export VAR`<br>
`hacker@dojo:~$ sh`<br>
`$ echo "VAR is: $VAR"`<br>
`VAR is: 1337`<br>

We can also combine the first two lines as `export VAR=1337`.<br><br>

Solution - export PWN=1337

# 5- Printing Exported Variables
`env` is a shell command for Unix and Unix-like operating systems. It is used to either print a list of environment variables or run another utility in an altered environment without having to modify the currently existing environment.

# 6- Storing Command Output
You will often want to store the output of some command into a variable. Luckily, the shell makes this quite easy using something called Command Substitution! Observe:<br><br>

`hacker@dojo:~$ FLAG=$(cat /flag)`<br>
`hacker@dojo:~$ echo "$FLAG"`<br>
`pwn.college{blahblahblah}`<br>
`hacker@dojo:~$`<br>

Solution - `PWN=$(/challenge/run)`
# 7- Reading Input
Here is an example using the -p argument, which lets you specify a prompt (otherwise, it would be hard for you, reading this now, to separate input from output in the example below):<br><br>

hacker@dojo:~$ read -p "INPUT: " MY_VARIABLE<br>
INPUT: Hello!<br>
hacker@dojo:~$ echo "You entered: $MY_VARIABLE"<br>
You entered: Hello!<br><br>

# 8- Reading Files
With `-p`: You can show a message to prompt the user before waiting for input.<br>
`hacker@dojo:~$ read -p "INPUT: " MY_VARIABLE`<br>
`INPUT: Hello!`<br>
`hacker@dojo:~$ echo "You entered: $MY_VARIABLE"`<br>
`You entered: Hello!`<br>

Without `-p`: It just waits for user input without any prompt.<br>
`INPUT: hacker@dojo:~$ echo $MY_VARIABLE`<br>
`OUTPUT:`<br>
`INPUT: hacker@dojo:~$ read MY_VARIABLE`<br>
`INPUT: Hello!`<br>
`INPUT: hacker@dojo:~$ echo "You entered: $MY_VARIABLE"`<br>
`OUTPUT: You entered: Hello!`<br><br>

Solution -<br>
`read PWN < /challenge/read_me`
