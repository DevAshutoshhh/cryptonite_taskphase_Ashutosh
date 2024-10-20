## 1. Matching with *
 The * wildcard matches any sequence of characters, replacing the argument with any file or directory that fits the pattern.
 Solution-
`cd /ch*`<br>
`ls`<br>
`./run  `<br>

## 2. Matching with ?
 The ? wildcard matches exactly one character. It works like *, but for single-character replacements.
  Solution-
`cd /?ha??enge  `<br>
`./run `<br>

## 3. Matching with []
 The [] wildcard matches one character from the specified set inside the brackets.
  Solution-
`cd /challenge/files`<br>
`/challenge/run file_[bash] `<br>

## 4. Matching paths with []
 The [] pattern can be used in pathnames as well to match specific characters in the directory or file names.
  Solution-
`/challenge/run /challenge/files/file_[bash]  `<br>

## 5. Mixing globs
 You can combine different wildcards in a single command to match more complex patterns.
  Solution-
`cd /challenge/files`<br>
`/challenge/run [chedpw]* `<br>

## 6. Exclusionary globbing
 The ! inside [] negates the match, excluding any files that start with the characters specified.
 Solution-
`cd /challenge/files`<br>
`/challenge/run [!pwn]* `<br>
