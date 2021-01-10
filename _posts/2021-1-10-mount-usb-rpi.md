---
layout: article
title: Mount USB storage on a Raspberry Pi
description: How to mount USB storage on a Raspberry Pi or other Linux device from the terminal.
published: 
---
Test 
## Mounting
To mount a USB drive so that the OS can use it, first, you need to know what it is recognised as.
```lsblk -f -p ```


Then, you will need to make a mount point. You can replace `myusb` with anything you like.
```sudo mkdir /mnt/myusb```


Then, use the following commands, based on what filesystem your USB defice uses. You can tell this from the first command, `lsblk -f -p`. Also, replace `/dev/sda1` and `/mnt/myusb` with what you decided before.


---
|FAT | sudo mount -t vfat /dev/sda1 /mnt/myusb -o umask=000 |
|exFAT| sudo apt install exfat-fuse && sudo mount -t exfat /dev/sda1 /mnt/myusb |
|ext4| sudo mount -t ext4 /dev/sda1 /mnt/myusb
|NTFS| sudo apt install ntfs-3g && sudo mount -t ntfs /dev/sda1 /mnt/myusb -o umask=000|
---
To unmount: 
`sudo umount /mnt/myusb
