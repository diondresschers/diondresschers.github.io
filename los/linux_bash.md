* Title: Linux - Bash
* File: cheatsheet\linux_bash.md
* By: Dion Dresschers
* Date: 2019-10-19
* Scope: Intergalactic
* License: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* (Version: 2019-10-19T06:36)

---

Shorten Prompt
```
$ PS1='\u:\W\$ '
```

# dd 

dd - convert and copy a file

* [How to clone disks with Linux dd command](https://www.howtoforge.com/tutorial/linux-dd-command-clone-disk-practical-example/)

```
dd if=/dev/oldsataspinningdisk of=/dev/newssd bs=64K conv=noerror,sync
```

# du

* [How To Find The Size Of A Directory In Linux - OSTechNix](https://www.ostechnix.com/find-size-directory-linux/)

`du -ha --max-depth=10 . | sort -
# rsync

rsync - a fast, versatile, remote (and local) file-copying tool

`dhdresschers@18-010872:/mnt/g/divg$ rsync -rv * /mnt/u/gschijf_volledige_backup_apotheek_2019-11015/`

This will rsync (-r) Recursive, and (-v) Verbose all from the source local current directory to the destination remote `/mnt/u/gschijf_volledige_backup_apotheek_2019-11015/`

* [13 Rsync Command Examples on Linux](https://www.fastwebhost.in/blog/13-rsync-command-examples-on-linux/)

# man

`man -k rsync # (equivalanent to whatis and equivalanet to apropos)`

# grep

# grep -r

Seach `recursive`, so in the current folder and subfolders for the string 'foo'.

`grep -r 'foo' .`

# grep -i

Search case `insensitive` for the string 'foo', so 'foo', 'Foo', 'FOO' and 'foO' will be found.

`grep -i 'foo' .` 

# grep -v 'foo'

Seach `inverse` for the string foo, so it will not find it. Great for piping into another line. So the result below will exclude all files with `csv` in the output.

`ls -l | grep -v 'csv'` 

## bash - grep -ri 'foo' .

Search for the string `foo`, `recursive` and case `insensitive` in this folder and all subfolders.

`grep -ri "searchstring" .` 

## bash - watch

watch (1)            - execute a program periodically, showing output fullscreen

```
watch -n 10 free # see every 10 seconds the output of the 'free' command
```

# ip + iproute2

```
# ip route list # local routing table, check the 'default' interface

# ip link # lever 2 info

# ip address show # ongeveer hetzelfde als ifconfig

```







# scripting

## scripting - bash

```bash
while true; do echo -n "The zipfile is now: ";ls -latrh *.zip ; sleep 1; done
```

## scripting - python

Here is some direct python direct in the bash command line without opening the python interpreter:

```bash
$ python -c "print(1/2)"
```



