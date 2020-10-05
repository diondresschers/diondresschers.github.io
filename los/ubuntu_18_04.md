# Ubuntu 18.04 Cheat Sheet

* License:  [Creative Commons - CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* By: Dion Dresschers
* Version: 2020-03-14 07:30:13

```bash
# Update and upgrade Ubuntu packages.
dion@desktop:~$ sudo apt-get update -y
dion@desktop:~$ sudo apt-get upgrade -y
# Check OS version.
dion@desktop:~$ cat /etc/*release* | grep -i "description"
DISTRIB_DESCRIPTION="Ubuntu 18.04.4 LTS"
```

