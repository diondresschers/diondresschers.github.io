
# Python 3 Cheat Sheet

* License:  [Creative Commons - CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* By: Dion Dresschers
* Version: 2020-03-14 07:35:39

```
# Check OS version.
dion@desktop:~$ cat /etc/*release* | grep -i "description"
DISTRIB_DESCRIPTION="Ubuntu 18.04.4 LTS"
```

```
# Check Python versions.
dion@desktop:~/data/git/python$ python --version
Python 2.7.17
dion@desktop:~$ python3 --version

Python 3.6.9
```

```
# Set up and activate a virtual environment
$ python3 -m venv v
$ cd v
$ source bin/activate
(v) /sentdex$ 
```

```
# Check Pyton version and install Kivy and Kivy Examples
(sentdex) kivy/sentdex$ python3 --version
Python 3.6.4 :: Anaconda, Inc.
(sentdex) kivy/sentdex$ python -m pip install kivy
(sentdex) kivy/sentdex$ python -m pip install kivy_examples
```

```
# Check pip version
dion@desktop:~/data/git/python$ pip --version
pip 19.0.2 from /usr/local/lib/python3.6/dist-packages/pip (python 3.6)
```

```
# Install virtualenv
dion@desktop:~$ sudo apt-get install python3-venv
```

```
# Create a new Virtual Environment and activate it
dion@desktop:~/data/git/python$ python3 -m venv v
dion@desktop:~/data/git/python$ cd v
dion@desktop:~/data/git/python/v$ source bin/activate
(v) dion@desktop:~/data/git/python/v$ 
```




