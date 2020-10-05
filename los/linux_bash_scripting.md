# variable, echo , date , log

```
dhdresschers@18-010872:/$ cat bash_script.txt
#!/bin/bash                                                                now=$(date +"%m_%d_%Y")                                                    file="test_$now.txt"                                                       echo "now starting the sync"                                               rsync -rv /mnt/g/divg/ /mnt/u/backup > $file.log                           ```