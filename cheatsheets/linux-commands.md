# Linux Commands Cheatsheet

## Navigation
| Command | What it does |
|---------|-------------|
| `pwd` | Show current directory |
| `ls` | List files in current directory |
| `ls -la` | List all files including hidden with details |
| `cd foldername` | Move into a folder |
| `cd ..` | Go back one folder |
| `cd ~` | Go to home directory |

## Files
| Command | What it does |
|---------|-------------|
| `cat filename` | Read a file |
| `nano filename` | Open file editor |
| `touch filename` | Create empty file |
| `cp file1 file2` | Copy a file |
| `mv file1 file2` | Move or rename a file |
| `rm filename` | Delete a file |

## Special Filename Tricks
| Situation | Solution |
|-----------|----------|
| Filename starts with dash | `cat ./-filename` |
| Filename has spaces | `cat "filename with spaces"` |
| Hidden files | `ls -la` |
| Case sensitive names | Check exact capitalisation |

## Search and Find
| Command | What it does |
|---------|-------------|
| `find . -size 1033c` | Find file by exact byte size |
| `find . -type f` | Find only files not directories |
| `find . -name "*.txt"` | Find by filename pattern |
| `file filename` | Identify file type |
| `file ./*` | Identify all files in directory |

## SSH
| Command | What it does |
|---------|-------------|
| `ssh user@host -p PORT` | Connect to remote server |
| `whoami` | Show current user |
| `exit` | Disconnect from SSH session |

## System
| Command | What it does |
|---------|-------------|
| `whoami` | Show current username |
| `echo text` | Print text to screen |
| `man command` | Read manual for any command |
| `ctrl+c` | Cancel running command |
| `ctrl+z` | Pause running command |
| `kill %1` | Kill paused background job |

## Nano Text Editor
| Command | What it does |
|---------|-------------|
| `nano filename` | Open or create file |
| `ctrl+x` | Exit nano |
| `y then enter` | Save when exiting |
| `ctrl+k` | Cut a line |
| `ctrl+u` | Paste a line |

## Searching Inside Man Pages
| Command | What it does |
|---------|-------------|
| `/-word` | Search for word inside man page |
| `n` | Jump to next search result |
| `q` | Quit man page |

## Permissions (ls -la output)
| Symbol | Meaning |
|--------|---------|
| `d` | Directory |
| `-` | Regular file |
| `r` | Read permission |
| `w` | Write permission |
| `x` | Execute permission |
| `.` | Current directory |
| `..` | Parent directory |
