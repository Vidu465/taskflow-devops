## Day 1 Linux Basics [30/06/2026]

**What I practiced:**
KodeKloud / Linux terminal labs + file handling + searching + redirection


## Commands I learned:

- `echo "text"` → prints text
- `>` → create file + write (overwrite)
- `>>` → add text to file (append)
- `cat file` → view file content
- `mkdir folder` → create a directory
- `rm -r folder` → delete directory
- `grep "text" file` → search inside files
- `grep -r` → search inside folders
- `grep -i` → ignore case
- `grep -l` → show only file names
- `grep -s` → hide errors
- `2>` → save error messages to a file
- `python3 script.py 2> error.txt` → save errors from Python script
- `zcat file.gz` → read compressed file without extracting
- `|` (pipe) → send output to another command
- `tee file` → show output + save to file
- `/mnt/d` → Windows D drive in Linux (WSL)
- `cd "/mnt/d/..."` → move into Windows folders safely

## File tasks I did:

- Created file with text using redirect:
```bash
echo "a file in my home directory" > file.txt
```

- Saved search result (file path) into a file:
```bash
grep -Rsl "172.16.238.197" /etc > /home/bob/ip
```

- Saved Python errors into a file:
```bash
python3 script.py 2> py_error.txt
```

- Read compressed man page into a file:
```bash
zcat /usr/share/man/man1/tail.1.gz > /home/bob/pipes
```


## What I now understand:

- `echo + >` is used to create/write files
- `grep` is used to search inside files and folders
- `2>` is used for error logging
- `|` connects commands together (pipe)
- `tee` shows output AND saves it
- `/mnt` is how Linux accesses Windows drives in WSL
- Spaces in Linux paths must be handled with `\` or quotes
- `.gz` files can be read without extracting using `zcat`


## Errors I faced:

`cd: too many arguments`
 caused by spaces in folder path (fixed using quotes or `\`)


## What I now understand overall:

- Linux is all about files, commands, and redirection
- Everything is either input, output, or error
- Paths matter a lot (Windows vs Linux format)
- Tools like `grep`, `tee`, `zcat` make work faster without extra steps
