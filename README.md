# Linux Command Reference for DevOps Engineers

A personal Linux command reference built throughout my DevOps journey.

Every command in this repository has been studied, tested, and practiced in real Linux environments as I continue developing my skills in DevOps, system administration, and cloud infrastructure.

This serves as both a learning archive and a long-term reference I will continue building throughout my career..

---

## 📚 Table of Contents

1. [File System Navigation](#1-file-system-navigation)
2. [File Viewing & Inspection](#2-file-viewing--inspection)
3. [Search & Discovery](#3-search--discovery)
4. [Text Processing Power](#4-text-processing-power)
5. [Pipes & Redirection](#5-pipes--redirection)
6. [Permissions & Ownership](#6-permissions--ownership)
7. [Users & Groups](#7-users--groups)
8. [Password & Authentication](#8-password--authentication)
9. [Disk & System Monitoring](#9-disk--system-monitoring)
10. [Process Management](#10-process-management)
11. [Networking](#11-networking)
12. [Archiving & Compression](#12-archiving--compression)
13. [System Information](#13-system-information)
14. [System & Service Management](#14-system--service-management)
15. [Package Management](#15-package-management)

---

## 1. File System Navigation 

| Command | My Definition / Logic | Flag / Example | Flag Definition |
|---|---|---|---|
| `pwd` | print the present working directory where i am right now. | -- | -- |
| `man` | opens the manual documentation for any command. | `man mkdir` | [man mkdir] |
| `ls` | listing the files and directories in a directory. | `ls /path/to/` | |
|  |  | `ls -l` | viewing the list in a (l)long listed format i.e [file size, file ownership, permissions e.t.c] |
|  |  | `ls -a` | viewing (a) all files inclusive of hidden files in the directory. |
|  |  | `ls -la` | viewing the list inclusive of hidden files in a long listed format. |
|  |  | `ls -lh` | viewing the list with the size in a (h) human readable format. |
|  |  | `ls -t` | sort files by time from the newest to the oldest. |
|  |  | `ls -R` | list directories recursively. |
|  |  | `ls -d/f` | list only files or directories. |
| `cd` | change directory from where I am to a new directory. | | |
|  |  | `cd ..` | move one directory up |
|  |  | `cd ~` | go to home directory |
|  |  | `cd -` | go to previous directory |
|  |  | `cd /` | go to root directory |
| `mkdir` | make a new directory. | `mkdir -p` | creating a directory from a parent dir. [ mkdir -p /home/script/{dir1,dir2,dir3} ] |
| `touch` | creating a new file. | `touch log{1..10}.log` | creating multiple files |
| `cp` | copying files from one location to another. | `cp -r` | copying all files from a directory to another recursively. |
|  |  | `cp -v` | verbose output (shows what is being copied). |
|  |  | `cp dir1/* dir2` | copying only files from one directory to another. |
| `mv` | moving a file or directory from one dir to another | `mv file.txt path/to/move.` | |
| `mv` | renaming a file or a directory | `mv old.name new.name.` | |
|  |  | `mv -v` | shows files being moved. |
| `rm` | removing a file or directory. | | |
|  |  | `rm -r` | removing a directory and all the files in it (r)recursively. |
|  |  | `rm -f` | removing a file by (f) forcefully. |
|  |  | `rm -rf` | force delete directories recursively without confirmation. [⚠⚠Cautious with this one] |
---

## 2. File Viewing & Inspection

| Command | My Definition / Logic | Flag / Example | Flag Definition |
|---|---|---|---|
| `cat` | cat [concatenate]→ show the content of a file. | `cat filex.txt` | |
|  |  | `cat -n` | print the content of a file and (n)numbering the lines in the file. |
|  |  | `cat file1 file2` | display multiple files. |
| `less` | print the context of a large file one page at a time. | `less -N` | print the file content on a single screen and number the lines. |
|  |  | `n/enter` | next line |
|  |  | `:b` | back to previous page |
|  |  | `space/pgUp/pgDn` | navigate the file pages |
|  |  | `q` | quit. |
| `more` | print file content in a page at a time unlike less no chance to move back just next. | `more +10 file.txt` | start at line 10. |
| `head` | print the first 10 lines of a file. | `head -n 20` | '-n' allows you to specify the number of lines you want to display from the top. |
|  |  | `head -c 50 file.txt` | first 50 characters. |
|  |  | `head -q file1 file2` | print content for both files. |
| `tail` | print the last 10 lines of a file. | `tail -n 20` | '-n' allows you to specify the number of lines you want to display from the bottom. |
|  |  | `tail -c 100 file.txt` | last 100 characters. |
|  |  | `tail -f server.log` | follow live log. |
| `nl` | print the content of a file and (n)number (l)lines in the file as output. | `nl -b a` | number all lines in a file. |
|  |  | `nl -b t` | number non-empty lines in a file. |
| `wc` | print the number of lines, number of words and number of characters in a file. | `wc -l` | print the number of (l)lines only in a file. |
|  |  | `wc -w` | print the number of (w) in the file. |
|  |  | `wc -c` | print the number of (c) characters/letters in a file. |
---

## 3. Search & Discovery

| Command | My Definition / Logic | Flag / Example | Flag Definition |
|---|---|---|---|
| `grep` | search for a specific pattern in a file. |  |  |
|  |  | `grep -v` | search a pattern in a file and exclude it in the output. |
|  |  | `grep -i` | search for a pattern and ignore the case. |
|  |  | `grep -n` | search a pattern and print the output with numbered lines. |
|  |  | `grep -r` | search a pattern in the entire directory and all directories and files in it (r) recursively. |
|  |  | `grep -c` | count the matches. |
|  |  | `grep -l` | show files containing matches. |
|  |  | `grep -E "word1\|word2\|word3" file_name` | search either of the words. |
|  |  | `grep "word1" \| grep "word2"` | Only shows lines that have BOTH keywords. |
|  |  | `grep -e "word1" -e "word 2" file_name` | finds lines containing "word1" OR "word2" |
|  |  | `grep -f file_input.txt search_file` | using a file with all the list of words to search |
| `find` | search for a pattern in the system |  |  |
|  |  | `find /path/ -name (name)` | search by name |
|  |  | `find /path/ -type (f/d)` | search by type file or directory |
|  |  | `find /path -size` | search by size |
|  |  | `find /path -iname` | search by name and ignore the case. |
|  |  | `find /path/ -mtime` | search by modification time |
|  |  | `find /path/ -type (f/d) -name  …. '-exec' command {}+` | finding a file or directory and executing commands to the output. |
|  |  | `-size unit & suffix` | c=bytes M=megabytes k=kilobytes G=gigabytes b=blocks |
| `locate` | search the location of a file in the system | `locate file.sh` |  |
|  |  | `locate -i` | search file location and ignore case. |
| `which` | search the executable path of a command. |  |  |
| `whereis` | search for a path of a command and returns all relevant paths. |  |  |
| `who -b` | view when the system was started. |  |  |

<p align="right"><a href="#kathys-linux-command-reference-for-devops">⬆ Back to Top</a></p>

