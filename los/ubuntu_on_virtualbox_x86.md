* Title: Cheatsheet - Ubuntu on VirtualBox
* Date: 2019-10-21
* File: cheatsheet\outlook.md
* Scope: Amsterdam UMC - Apotheek
* License: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 
* Version: 2019-10-21T11:52

# Install Virtual Box Guest Additions

* VirtualBox -> Menu -> Devices -> Insert Guest Additions CD image...

# General settings

* VirtualBox -> Menu -> Drag and Drop -> Bidirectional
* VirtualBox -> Menu -> Shared Clipboard -> Bidirectionalc

# Folders

* VirtualBox -> Menu -> Devices -> Shared Folder -> Shared Folder Settings... 

"Shared Folders" -> "Machine Folders" -> "Adds new shared folder."

* Folder Path: C:\Users\dhdresschers\data
* Folder Name: data
* Read-only: FALSE
* Auto-mount: TRUE
* Mount point: /mnt/data
* Make Permanent: TRUE

```
dhdresschers@ubuntu-vm: cd /mnt/data
bash: cd: /mnt/data: Persmission denied
```

# Enable network:

VirtualBox -> Menu -> 'Settings' -> 'Network'-tab -> 'Advanced'-expand -> 'Cable Connected'-checkbox = True

# Make sure you can SSH from your host to your vm

VirtualBox -> Menu -> 'Settings' -> 'Network'-tab -> 'Advanced'-expand -> 'Port Forwarding'

This is an example:

|Name|Protocol|Host IP|Guest IP|Guest Port|
|----|--------|-------|--------|----------|
|SSH |TCP     |127.0.0.2|22|10.0.2.15|22|

```
dhdresschers@19-001596:/mnt/c/Users/dhdresschers/data/git/md$ ssh 
dhdresschers@127.0.0.2's password:
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 5.0.0-31-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage


 * Canonical Livepatch is available for installation.
   - Reduce system reboots and improve kernel security. Activate at:
     https://ubuntu.com/livepatch

6 packages can be updated.
0 updates are security updates.

Your Hardware Enablement Stack (HWE) is supported until April 2023.
*** System restart required ***
Last login: Thu Oct 24 14:34:33 2019 from 10.0.2.2
dhdresschers@ubuntu-vm:~$
```