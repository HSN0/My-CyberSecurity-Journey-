# OverTheWire Bandit — Levels 0 to 5

## Level 0
**Concept:** SSH basics
**Command:** `ssh bandit0@bandit.labs.overthewire.org -p 2220`
**What I learned:**
- SSH requires -p flag for non-default ports
- Password is hidden when typing — normal Linux behavior
- Always check your prompt to know which machine you are on

## Level 1
**Concept:** Files named with special characters (dash)
**Command:** `cat ./-`
**What I learned:**
- A dash alone means "read from keyboard" to Linux
- ./ tells Linux to treat the name as a file path not a flag
- Structure: cat [path][filename]

## Level 2
**Concept:** Filenames with spaces and leading dashes
**Command:** `cat "./--spaces in this filename--"`
**What I learned:**
- Quotes group everything inside into one argument
- Without quotes Linux splits on spaces treating each word as a separate filename
- Permission denied = file EXISTS but access blocked
- No such file or directory = file does not exist
- Both ./ and quotes needed when filename has dashes AND spaces

## Level 3
**Concept:** Hidden files and directories
**Commands:**
- `ls -la` to reveal hidden files
- `cd inhere` to enter directory
- `cat "./...Hiding-From-You"`
**What I learned:**
- Files starting with a dot are hidden from plain ls
- The -a flag in ls -la reveals hidden files
- Linux is case sensitive — You and you are different filenames
- d at start of permissions means directory

## Level 4
**Concept:** Identifying file types among multiple files
**Commands:**
- `file ./-file*` to check all files at once
- `cat ./-file07` to read the correct file
**What I learned:**
- file command identifies file types without opening them
- Wildcard * checks multiple files in one command
- Only -file07 returned ASCII text — rest were binary data
- Same technique used in real pentesting to triage files on compromised systems

## Level 5
**Concept:** Finding files by specific criteria across many directories
**Command:** `find . -size 1033c`
**What I learned:**
- find searches recursively through all directories
- -size with c suffix specifies exact byte count
- One command searched 20 directories instantly
- Real pentesting use: finding config files, SSH keys, SUID binaries
- Same structure, different criteria for different tasks
