
# Kivy Cheat Sheet

* License:  [Creative Commons - CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* By: Dion Dresschers
* Version: 2020-03-14 06:03:06

```bash
# Check OS version.
dion@desktop:~$ cat /etc/*release* | grep -i "description"
DISTRIB_DESCRIPTION="Ubuntu 18.04.4 LTS"
```


```bash
# Set up and activate a virtual environment
$ python3 -m venv v
$ cd v
$ source bin/activate
(v) /sentdex$ 
```

```bash
# Check Pyton version and install Kivy and Kivy Examples
(sentdex) kivy/sentdex$ python3 --version
Python 3.6.4 :: Anaconda, Inc.
(sentdex) kivy/sentdex$ python -m pip install kivy
(sentdex) kivy/sentdex$ python -m pip install kivy_examples
```