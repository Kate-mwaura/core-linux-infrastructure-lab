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
