## 1- Listing Processes

In the majority of cases, this is all that you'll see with a default ps. To make it useful, we need to pass a few arguments.<br>

As ps is a very old utility, its usage is a bit of a mess. There are two ways to specify arguments.<br>

"Standard" Syntax: in this syntax, you can use `-e` to list "every" process and `-f` for a "full format" output, including arguments. These can be combined into a single argument `-ef`.<br>

"BSD" Syntax: in this syntax, you can use `a` to list processes for all users, `x` to list processes that aren't running in a terminal, and `u` for a "user-readable" output. 
These can be combined into a single argument aux.<br>

These two methods, `ps -ef` and `ps aux` result in slightly different, but cross-recognizable output.<br>

Solution -<br>
`ps aux`<br>

## 2- Killing Processes

We use `KILL` to kill a command<br>

Solution-<br>
`ps -ef | grep /challenge/dont_run`<br>
`kill 76 `<br>
`/challenge/run`<br>

## 3- Interrupting processes 
We use `ctrl C` to interrupt a running process<br>
Solution-<br>
`/challenge/run`<bg>
`Ctrl C`<br>

## 4- Suspending Processes
We use `Ctrl Z` to suspend a processes<br>
Solution-<br>
`/challenge/run`<br>
`Ctrl+Z`<br>
`/challenge/run`<br>

## 5- Resuming Processes
your shell provides the `fg` command, a builtin that takes the suspended process, resumes it, and puts it back in the foreground of your terminal.<br>
Solution-<br>
`/challenge/run`<br>
`Ctrl+Z`<br>
`fg`<br>

## 6- Backgrounding Processes
You've resumed processes in the foreground with the `fg` command. You can also resume processes in the background with the `bg` command!<br>
This will allow the process to keep running, while giving you your shell back to invoke more commands in the meantime.<br>
Solution-<br>
`/challenge/run`<br>
`Ctrl+Z`<br>
`bg`<br>
`/challenge/run`<br>

## 7- Foregrounding Processes
Solution -<br>
`/challenge/run`<br>
`Ctrl+Z`<br>
`bg`<br>
`fg`<br>

## 8- Starting background processes
you don't have to suspend processes to background them: you can start the backgrounded right off the bat! It's easy; all you have to do is append a `&` to the command,<br>
Solution-<br>
`/challenge/run &`<br>

## 9- Process Exit Codes
You can access the exit code of the most recently-terminated command using the special `?` variable (don't forget to prepend it with `$` to read its value!)<br>
Solution-<br>
`/challenge/get-code`<br>
`echo $?`<br>
`/challenge/submit-code 16`<br>
