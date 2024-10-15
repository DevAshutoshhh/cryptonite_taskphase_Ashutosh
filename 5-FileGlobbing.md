# 1. Matching with *
# The * wildcard matches any sequence of characters, replacing the argument with any file or directory that fits the pattern.
cd /ch*
ls
./run  

# 2. Matching with ?
# The ? wildcard matches exactly one character. It works like *, but for single-character replacements.
cd /?ha??enge  
./run 

# 3. Matching with []
# The [] wildcard matches one character from the specified set inside the brackets.
cd /challenge/files
/challenge/run file_[abhs] 

# 4. Matching paths with []
# The [] pattern can be used in pathnames as well to match specific characters in the directory or file names.
/challenge/run /challenge/files/file_[absh]  

# 5. Mixing globs
# You can combine different wildcards in a single command to match more complex patterns.
cd /challenge/files
/challenge/run [chedpw]* 

# 6. Exclusionary globbing
# The ! inside [] negates the match, excluding any files that start with the characters specified.
cd /challenge/files
/challenge/run [!pwn]* 
