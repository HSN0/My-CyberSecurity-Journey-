# OverTheWire Bandit — Levels 6 to 14

## Level 6
**Concept:** Searching entire filesystem with multiple criteria
**Command:** `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`
**What I learned:**
- Search from / to cover the entire filesystem not just current folder
- Combine -user, -group, and -size in one find command
- 2>/dev/null hides permission denied errors from output
- Multiple criteria narrow results dramatically

## Level 7
**Concept:** Searching for a specific word inside a large file
**Command:** `grep millionth data.txt`
**What I learned:**
- grep searches for a word inside a file and returns matching lines
- Structure: grep "word" filename
- Much faster than reading a massive file manually

## Level 8
**Concept:** Finding the only unique line in a file full of duplicates
**Command:** `sort data.txt | uniq -c | grep "^ *1 "`
**What I learned:**
- sort arranges lines alphabetically so duplicates sit together
- uniq -c counts consecutive duplicate lines
- Piping combines commands — output of one feeds into the next
- uniq only works correctly on sorted data

## Level 9
**Concept:** Extracting readable text from binary data
**Command:** `strings data.txt`
**What I learned:**
- strings extracts human-readable text from binary files
- Binary files contain non-printable characters mixed with real data
- cat on a binary file produces garbage — strings filters it
- Used in real malware analysis to extract readable content

## Level 10
**Concept:** Base64 decoding
**Command:** `base64 -d data.txt`
**What I learned:**
- base64 without flags ENCODES — adds -d flag to DECODE
- Base64 is not encryption — it is encoding, easily reversible
- Common in web tokens, email attachments, and obfuscated data

## Level 11
**Concept:** ROT13 cipher decoding
**Command:** `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`
**What I learned:**
- tr translates characters — substitutes one set for another
- ROT13 shifts each letter 13 positions forward in the alphabet
- Applying ROT13 twice returns to the original — same command decodes
- tr is useful for log parsing and basic text manipulation

## Level 12
**Concept:** Multi-layer compression forensics
**Commands used in sequence:**
- `xxd -r data.txt > data.out` — reverse hexdump to binary
- `file data.out` — identify compression type
- `mv data.out data.out.gz && gunzip data.out.gz` — decompress gzip
- `mv data.out data.out.bz2 && bunzip2 data.out.bz2` — decompress bzip2
- `tar -xf data.out` — extract tar archive
- Repeated until ASCII text reached
**What I learned:**
- xxd -r reverses a hexdump back into binary data
- file command is essential for identifying unknown file types
- Files must have correct extension before decompression tools work
- Real malware often uses multiple compression layers to hide payloads
- Patience and systematic approach beats guessing

## Level 13
**Concept:** SSH private key authentication
**Command:** 
- Found sshkey.private in home directory
- `chmod 600 ~/bandit14.key` — set correct permissions
- `ssh -i ~/bandit14.key bandit14@bandit.labs.overthewire.org -p 2220`
**What I learned:**
- SSH can authenticate with a private key instead of a password
- chmod 600 sets file to owner-read-only — SSH refuses keys that are too open
- -i flag specifies the identity/key file to use
- Private keys are used constantly in real server administration and pentesting

## Level 14
**Concept:** Reading password files with correct permissions
**Command:** `cat /etc/bandit_pass/bandit14`
**What I learned:**
- /etc/bandit_pass/ stores passwords only readable by each respective user
- File permissions control who can read sensitive system files
- Same concept applies to /etc/shadow on real Linux systems