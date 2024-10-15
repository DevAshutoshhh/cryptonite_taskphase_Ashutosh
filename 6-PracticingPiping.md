## 1-Redirecting Output  
Output can be redirected using the `>` character.  
Solution:  
`echo PWN > COLLEGE`

## 2-Redirecting More Output  
Output from any command can be redirected.  
Solution:  
`/challenge/run > myflag`<br>
`cat myflag`<br> 


## 3-Appending Output  
The `>>` operator appends output to an existing file.  
Solution:  
`/challenge/run >> /home/hacker/the-flag`<br>  
`echo stdout >> /home/hacker/the-flag`<br>  
`cat /home/hacker/the-flag`<br>  

## 4-Redirecting Errors  
File descriptors are numbers used to manage input/output streams in Linux.
Solution:  
`/challenge/run > myflag 2> instructions`<br>  
`cat myflag`<br>  

## 5-Redirecting Inputs  
The `<` symbol is used to redirect input from a file.  
Solution:  
`echo COLLEGE > PWN`<br>  
`/challenge/run < PWN`<br>

## 6-Grepping Stored Results  
`grep` is used to search for specific patterns in files or input streams.  
Solution:  
`/challenge/run > /tmp/data.txt`<br>  
`grep pwn.college /tmp/data.txt`<br>

## 7-Grepping Live Results  
The `|` operator pipes the output of one command as input to another.  
Solution:  
`/challenge/run | grep pwn.college`<br>

## 8-Grepping Errors  
`>&` redirects one file descriptor to another.  
Solution:  
`/challenge/run 2>&1 | grep pwn.college`<br>

## 9-Duplicating Piped Data with Tee  
`tee` duplicates data flowing through pipes and stores it in files.  
Solution:  
`touch random`.  
`/challenge/pwn | tee random | /challenge/college`  
`cat random`
`/challenge/pwn --secret [arg] | /challenge/college` to get the flag.  
`cat random`  
`/challenge/pwn --secret [arg] | /challenge/college`

## 10-Writing to Multiple Programs  
`tee` can duplicate output to multiple commands.  
Solution:  


## 11-Split-piping stderr and stdout  
Solution:  
`/challenge/hack > >(/challenge/planet) 2> >(/challenge/the)`  
