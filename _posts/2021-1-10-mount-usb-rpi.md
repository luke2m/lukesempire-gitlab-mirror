---
layout: article
title: Mount USB storage on a Raspberry Pi
description: How to mount USB storage on a Raspberry Pi or other Linux device from the terminal.
published: 
---
Test 
lsblk -f -p
sudo mkdir /mnt/myusb
---
FAT: sudo mount -t vfat /dev/sda1 /mnt/myusb -o umask=000
exFAT: sudo apt install exfat-fuse && sudo mount -t exfat /dev/sda1 /mnt/myusb
ext4: sudo mount -t ext4 /dev/sda1 /mnt/myusb
NTFS: sudo apt install ntfs-3g && sudo mount -t ntfs /dev/sda1 /mnt/myusb -o umask=000
---
sudo umount /mnt/myusb
