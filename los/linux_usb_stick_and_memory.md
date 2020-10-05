# before adding usb

## dmesg | tail

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ # before adding usb
dion@desktop:~/data/git/md/ptvd/cheatsheet$ dmesg | tail
[ 9134.939650] usb 1-1.6: New USB device strings: Mfr=3, Product=4, SerialNumber=2
[ 9134.939652] usb 1-1.6: Product: USB Storage
[ 9134.939654] usb 1-1.6: Manufacturer: Generic
[ 9134.939655] usb 1-1.6: SerialNumber: 000000000272
[ 9134.940499] usb-storage 1-1.6:1.0: USB Mass Storage device detected
[ 9134.940677] scsi host6: usb-storage 1-1.6:1.0
[ 9135.948221] scsi 6:0:0:0: Direct-Access     Generic  STORAGE DEVICE   0272 PQ: 0 ANSI: 0
[ 9135.948804] sd 6:0:0:0: Attached scsi generic sg3 type 0
[ 9137.720295] sd 6:0:0:0: [sdc] Attached SCSI removable disk
[ 9515.527551] usb 1-1.6: USB disconnect, device number 9
```

## lsusb

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ lsusb
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 004: ID 2516:0059  
Bus 001 Device 003: ID 03f0:094a Hewlett-Packard Optical Mouse [672662-001]
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 003 Device 002: ID 28de:1142  
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

## lsblk

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ # before adding usb
dion@desktop:~/data/git/md/ptvd/cheatsheet$ lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
loop0    7:0    0  16,2M  1 loop /snap/vice-jz/22
loop1    7:1    0 456,4M  1 loop /snap/wine-platform/128
loop2    7:2    0  26,2M  1 loop /snap/heroku/3828
loop3    7:3    0 320,9M  1 loop /snap/pycharm-community/155
loop4    7:4    0 420,9M  1 loop /snap/pycharm-professional/154
loop5    7:5    0 456,4M  1 loop /snap/wine-platform/125
loop6    7:6    0 114,4M  1 loop /snap/fsuae/43
loop7    7:7    0    89M  1 loop /snap/core/7713
loop8    7:8    0 192,1M  1 loop /snap/eclipse/29
loop9    7:9    0   132K  1 loop /snap/gtk2-common-themes/5
loop10   7:10   0  26,2M  1 loop /snap/heroku/3832
loop11   7:11   0    74M  1 loop /snap/wine-platform-3-stable/6
loop12   7:12   0 114,4M  1 loop /snap/fsuae/39
loop13   7:13   0  42,8M  1 loop /snap/gtk-common-themes/1313
loop14   7:14   0 101,5M  1 loop /snap/p7zip-desktop/220
loop15   7:15   0 184,8M  1 loop /snap/eclipse/40
loop16   7:16   0 217,3M  1 loop /snap/wine-platform-runtime/37
loop17   7:17   0  92,5M  1 loop /snap/freac/247
loop18   7:18   0  50,7M  1 loop /snap/p7zip-desktop/163
loop19   7:19   0  54,5M  1 loop /snap/core18/1192
loop20   7:20   0  89,1M  1 loop /snap/core/7917
loop21   7:21   0  54,5M  1 loop /snap/core18/1223
loop22   7:22   0  89,2M  1 loop /snap/qucs-spice/4
loop23   7:23   0  16,2M  1 loop /snap/vice-jz/47
loop24   7:24   0  16,2M  1 loop /snap/vice-jz/20
loop25   7:25   0 309,5M  1 loop /snap/phpstorm/116
loop26   7:26   0   3,9M  1 loop /snap/notepad-plus-plus/212
loop27   7:27   0 456,4M  1 loop /snap/wine-platform/122
loop28   7:28   0 320,2M  1 loop /snap/pycharm-community/150
loop29   7:29   0   215M  1 loop /snap/wine-platform-runtime/48
loop30   7:30   0 149,9M  1 loop /snap/gnome-3-28-1804/71
loop31   7:31   0  44,2M  1 loop /snap/gtk-common-themes/1353
loop32   7:32   0 421,2M  1 loop /snap/pycharm-professional/159
loop33   7:33   0  17,9M  1 loop /snap/pdftk/9
loop34   7:34   0 149,9M  1 loop /snap/gnome-3-28-1804/67
loop35   7:35   0   310M  1 loop /snap/phpstorm/120
loop36   7:36   0   132K  1 loop /snap/gtk2-common-themes/4
loop37   7:37   0   3,9M  1 loop /snap/notepad-plus-plus/207
sda      8:0    0   1,8T  0 disk 
└─sda1   8:1    0   1,8T  0 part /
sdb      8:16   0   1,8T  0 disk 
├─sdb1   8:17   0   500M  0 part 
├─sdb2   8:18   0   1,8T  0 part 
└─sdb3   8:19   0   848M  0 part 
sr0     11:0    1  1024M  0 rom  
```

## fdisk -l

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ sudo fdisk -l | grep sd
[sudo] password for dion: 
Disk /dev/sda: 1,8 TiB, 2000398934016 bytes, 3907029168 sectors
/dev/sda1  *     2048 3907028991 3907026944  1,8T 83 Linux
Disk /dev/sdb: 1,8 TiB, 2000398934016 bytes, 3907029168 sectors
/dev/sdb1  *          2048    1026047    1024000  500M  7 HPFS/NTFS/exFAT
/dev/sdb2          1026048 3905287310 3904261263  1,8T  7 HPFS/NTFS/exFAT
/dev/sdb3       3905288192 3907024895    1736704  848M 27 Hidden NTFS WinRE
```

# after adding usb

## dmesg | tail

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ dmesg | tail
[ 9572.946476] print_req_error: I/O error, dev sdc, sector 0
[ 9572.946478] Buffer I/O error on dev sdc, logical block 0, async page read
[ 9572.947737] sd 6:0:0:0: [sdc] tag#0 FAILED Result: hostbyte=DID_OK driverbyte=DRIVER_SENSE
[ 9572.947739] sd 6:0:0:0: [sdc] tag#0 Sense Key : Not Ready [current] 
[ 9572.947741] sd 6:0:0:0: [sdc] tag#0 Add. Sense: Medium not present
[ 9572.947744] sd 6:0:0:0: [sdc] tag#0 CDB: Read(10) 28 00 00 00 00 18 00 00 08 00
[ 9572.947745] print_req_error: I/O error, dev sdc, sector 24
[ 9572.947747] Buffer I/O error on dev sdc, logical block 3, async page read
[ 9572.950374]  sdc: unable to read partition table
[ 9572.951142] sd 6:0:0:0: [sdc] Attached SCSI removable disk
```

## lsusb

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ lsusb
Bus 002 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 010: ID 05e3:0736 Genesys Logic, Inc. microSD Reader/Writer
Bus 001 Device 004: ID 2516:0059  
Bus 001 Device 003: ID 03f0:094a Hewlett-Packard Optical Mouse [672662-001]
Bus 001 Device 002: ID 8087:0024 Intel Corp. Integrated Rate Matching Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 003 Device 002: ID 28de:1142  
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

## lsblk - after adding usb

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
loop0    7:0    0  16,2M  1 loop /snap/vice-jz/22
loop1    7:1    0 456,4M  1 loop /snap/wine-platform/128
loop2    7:2    0  26,2M  1 loop /snap/heroku/3828
loop3    7:3    0 320,9M  1 loop /snap/pycharm-community/155
loop4    7:4    0 420,9M  1 loop /snap/pycharm-professional/154
loop5    7:5    0 456,4M  1 loop /snap/wine-platform/125
loop6    7:6    0 114,4M  1 loop /snap/fsuae/43
loop7    7:7    0    89M  1 loop /snap/core/7713
loop8    7:8    0 192,1M  1 loop /snap/eclipse/29
loop9    7:9    0   132K  1 loop /snap/gtk2-common-themes/5
loop10   7:10   0  26,2M  1 loop /snap/heroku/3832
loop11   7:11   0    74M  1 loop /snap/wine-platform-3-stable/6
loop12   7:12   0 114,4M  1 loop /snap/fsuae/39
loop13   7:13   0  42,8M  1 loop /snap/gtk-common-themes/1313
loop14   7:14   0 101,5M  1 loop /snap/p7zip-desktop/220
loop15   7:15   0 184,8M  1 loop /snap/eclipse/40
loop16   7:16   0 217,3M  1 loop /snap/wine-platform-runtime/37
loop17   7:17   0  92,5M  1 loop /snap/freac/247
loop18   7:18   0  50,7M  1 loop /snap/p7zip-desktop/163
loop19   7:19   0  54,5M  1 loop /snap/core18/1192
loop20   7:20   0  89,1M  1 loop /snap/core/7917
loop21   7:21   0  54,5M  1 loop /snap/core18/1223
loop22   7:22   0  89,2M  1 loop /snap/qucs-spice/4
loop23   7:23   0  16,2M  1 loop /snap/vice-jz/47
loop24   7:24   0  16,2M  1 loop /snap/vice-jz/20
loop25   7:25   0 309,5M  1 loop /snap/phpstorm/116
loop26   7:26   0   3,9M  1 loop /snap/notepad-plus-plus/212
loop27   7:27   0 456,4M  1 loop /snap/wine-platform/122
loop28   7:28   0 320,2M  1 loop /snap/pycharm-community/150
loop29   7:29   0   215M  1 loop /snap/wine-platform-runtime/48
loop30   7:30   0 149,9M  1 loop /snap/gnome-3-28-1804/71
loop31   7:31   0  44,2M  1 loop /snap/gtk-common-themes/1353
loop32   7:32   0 421,2M  1 loop /snap/pycharm-professional/159
loop33   7:33   0  17,9M  1 loop /snap/pdftk/9
loop34   7:34   0 149,9M  1 loop /snap/gnome-3-28-1804/67
loop35   7:35   0   310M  1 loop /snap/phpstorm/120
loop36   7:36   0   132K  1 loop /snap/gtk2-common-themes/4
loop37   7:37   0   3,9M  1 loop /snap/notepad-plus-plus/207
sda      8:0    0   1,8T  0 disk 
└─sda1   8:1    0   1,8T  0 part /
sdb      8:16   0   1,8T  0 disk 
├─sdb1   8:17   0   500M  0 part 
├─sdb2   8:18   0   1,8T  0 part 
└─sdb3   8:19   0   848M  0 part 
sr0     11:0    1  1024M  0 rom  
```

## fdisk -l

```
dion@desktop:~/data/git/md/ptvd/cheatsheet$ sudo fdisk -l | grep sd
[sudo] password for dion: 
Disk /dev/sda: 1,8 TiB, 2000398934016 bytes, 3907029168 sectors
/dev/sda1  *     2048 3907028991 3907026944  1,8T 83 Linux
Disk /dev/sdb: 1,8 TiB, 2000398934016 bytes, 3907029168 sectors
/dev/sdb1  *          2048    1026047    1024000  500M  7 HPFS/NTFS/exFAT
/dev/sdb2          1026048 3905287310 3904261263  1,8T  7 HPFS/NTFS/exFAT
/dev/sdb3       3905288192 3907024895    1736704  848M 27 Hidden NTFS WinRE
```

So it seems there is filesystem shown on the usb device

## fdisk 

```
dion@desktop:~/Downloads$ sudo fdisk /dev/sdc

Welcome to fdisk (util-linux 2.31.1).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

fdisk: cannot open /dev/sdc: No medium found
```

## dd

```
dion@desktop:~/Downloads$ sudo dd bs=4M if=ubuntu-19.10-preinstalled-server-armhf+raspi3.img of=/dev/sdc conv=fsync
672+1 records in
672+1 records out
2822575104 bytes (2,8 GB, 2,6 GiB) copied, 406,109 s, 7,0 MB/s
```


* [How to clone disks with Linux dd command](https://www.howtoforge.com/tutorial/linux-dd-command-clone-disk-practical-example/)

sudo fdisk -l /dev/sdb # check for the 'end' count

```
dd if=/dev/sdb bs=512 count =44898303 conv=sync,noerror | pv -s 21G | dd of=/dev/sdc
```

```
dd if=/dev/oldsataspinningdisk of=/dev/newssd bs=64K conv=noerror,sync

# check de hardware van een disk:

`hdparm -I /dev/sda`

# check all disks

`lshw -class disk -class storage

# check health hard disk

`smartctl -a /dev/sda`

