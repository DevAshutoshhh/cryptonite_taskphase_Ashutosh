## 1 CAT 
to cat form flag in `cd` using cat `flag`

## 2 CATTING ABSOLUTE PATHS
to cat a flag using its relative path use `cat /flag`

## 3 MORE CATTING PRACTISE
finding the path of flag using -
`find / -name "flag"` 
 and then different paths were given i checked the right absolute path then used cat (absolutepath)
 
## 4 GREPPING 
for grepping we use` grep anythingyouknowaboutfile-like pattern filename`

`grep pwn.college /challenge/data.txt`

## 5 LISTING FILES
ls to list content of challenge directory and then access the renamed run
solution-
cd /challenge
./2626-renamed-run-30825

## 6 Touching Files 
Touch is used to create files(blank) in directories

in this challange we had to create 2 files in tmp dir then executr `/challenge/run`

## 7 Removing Files

used `rm` to remove delete me from the `cd`
`cd`
`rm delete_me`
`/challenge/check`

## 8 hidden files

used `cd /` then `ls -a` to get hidden files then `cat .flag-36287390 `

## 9 AN EPIC FILE SYSTEM
there were clues given to find flag using the given requirments
```

hacker@commands~an-epic-filesystem-quest:/home$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
SECRET  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat SECRET
Great sleuthing!
The next clue is in: /opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed$ ls
BRIEF  __init__.pyi  wsgi.pyi  xml.pyi
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed$ cat BRIEF
Lucky listing!
The next clue is in: /usr/share/doc/libunibilium4

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed$ ls -a /usr/share/doc/libunibilium4
.  ..  SPOILER-TRAPPED  changelog.Debian.gz  copyright
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed$ cat /usr/share/doc/libunibilium4/SPOILER-TRAPPED
Great sleuthing!
The next clue is in: /usr/lib/python3/dist-packages/OpenSSL

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/stdlib/2and3/_typeshed$ cd /usr/lib/python3/dist-packages/OpenSSL
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/OpenSSL$ ls
SSL.py  TEASER  __init__.py  __pycache__  _util.py  crypto.py  debug.py  rand.py  tsafe.py  version.py
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/OpenSSL$ cat TEASER
Congratulations, you found the clue!
The next clue is in: /usr/share/icons/hicolor/512x512/actions
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/OpenSSL$ cd /usr/share/icons/hicolor/512x512/actions
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/512x512/actions$ ls
LEAD
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/512x512/actions$ cat LEAD
Lucky listing!
The next clue is in: /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/512x512/actions$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ ls
POINTER  __init__.py  __pycache__  _in_process.py
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat POINTER
Yahaha, you found me!
The next clue is in: /usr/share/locale/he

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ ls -a /usr/share/locale/he
.  ..  LC_MESSAGES  WHISPER-TRAPPED
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat WHISPER-TRAPPED
cat: WHISPER-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat /usr/share/locale/he/WHISPER-TRAPPED
Yahaha, you found me!
The next clue is in: /opt/ghidra/Ghidra/Features/GhidraServer/data/yajsw-stable-13.09/lib/extended

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ la -a /opt/ghidra/Ghidra/Features/GhidraServer/data/yajsw-stable-13.09/lib/extended
.  ..  ReadMe.txt  SNIPPET-TRAPPED  abeille  commons  cron  glazedlists  groovy  jgoodies  keystore  regex  sigar  slf4j  velocity  vfs-dbx  vfs-webdav  yajsw
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat /opt/ghidra/Ghidra/Features/GhidraServer/dat
a/yajsw-stable-13.09/lib/extended/SNIPPET-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/tornado/test/gettext_translations/fr_FR

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ ls -a /usr/lib/python3/dist-packages/tornado/test/gettext_translations/fr_FR
.  ..  .TRACE  LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat .TRACE
cat: .TRACE: No such file or directory
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ cat /usr/lib/python3/dist-packages/tornado/test/
gettext_translations/fr_FR/.TRACE
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{Ua8E4GB4FR-oMXigNUsSf8a9XWy.dljM4QDLzQTO0czW}
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_vendor/pyproject_hooks/_in_process$ 
```
## 10 Making directories 

to make directories using ` mkdir path\name`

## 11 finding files 

to find files at given location 
`find / -name flag -type f`
then access using cat `(path found)`


