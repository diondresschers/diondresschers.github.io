# Shortcut Menu's

* [Make Windows 10 Underline and Highlight Menu Shortcut Keys](https://www.groovypost.com/howto/make-windows-10-highlight-underline-menu-shortcut-keys/)

To underline menu letter, so you can access the menu with <ALT> + the specific letter:

Windows 10 -> 'Windows'/'Super'key -> Type 'Underline access keys shortcuts in menus when avaialable' -> Change the value of 'Underline access keys when available' from False to True.

# change the ALT-TAB view from preview to program icon's

* [Windows 10: How To Enable the old-style Alt + Tab - TechNet Articles - United States (English) - TechNet Wiki](https://social.technet.microsoft.com/wiki/contents/articles/52222.windows-10-how-to-enable-the-old-style-alt-tab.aspx)

To enable the "old style" Alt + Tab applications switching GUI, perform the following operations

1. open the Windows Registry Editor and go to HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer
1. create a new 32-bit DWORD value named AltTabSettings and set its value to 1
1. sign out from your Windows session and sign again (or reboot your PC) for the change to become effective 

# WSL

## WSL - Mounting 

in je `~/.bashrc` voeg op het einde:

```
sudo mkdir /mnt/g
sudo mkdir /mnt/u
sudo mount -t drvfs G: /mnt/g
sudo mount -t drvfs U: /mnt/u
```


# Install Jupyter Notebook in WSL

* [Jupyter Notebook in Windows subsystem for Linux (WSL)](https://medium.com/@sayanghosh_49221/jupyter-notebook-in-windows-subsystem-for-linux-wsl-f075f7ec8691)

```
sudo apt update 
sudo apt upgrade
sudo apt install python3 python3-pip ipython3
python3 --version # test
pip3 install jupyter
vi ~/.bashrc
```

Add under the line "esac":

`alias jupyter-notebook="~/.local/bin/jupyter-notebook --no-browser"`

and save the file.

```
source ~/.bashrc
jupyter notebook
```


# References


