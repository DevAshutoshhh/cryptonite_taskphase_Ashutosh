## 1-The PATH Variable
The PATH variable contains directories where the shell looks for programs.<br>
Without the PATH, commands like 'ls', 'cd', etc., won't work.<br>
In this challenge, we export an empty PATH and attempt to run a script.<br>

Solution-
`export PATH`<br>
`PATH=""`<br>
`/challenge/run`<br>

## 2-Setting PATH
We can add new directories to the PATH variable, allowing us to run custom commands.<br>
In this challenge, we overwrite the existing PATH to run commands from a different directory.<br>

Solution-
`export PATH`<br>
`PATH=/challenge/more_commands/`<br>
`/challenge/run`<br>

## 3-Adding Commands
Here, we create a custom 'win' command that outputs the flag.<br>
Instead of overwriting PATH, we append our custom directory to it.<br>

Solution-
`echo "cat /flag" > win`<br>
`chmod +x win`<br>
`echo $PATH`<br>
`PATH="$PATH:/home/hacker"`<br>
`echo $PATH`<br>
`/challenge/run`<br>

## 4-Hijacking Commands
In this challenge, we hijack the 'rm' command by creating our own version and placing it earlier in the PATH.<br>
This forces the shell to run our custom 'rm' instead of the system's version.<br>

Solution-
`PATH=/home/hacker:$PATH`<br>
`echo "cat /flag" > rm`<br>
`chmod +x rm`<br>
`/challenge/run`<br>

