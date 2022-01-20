---
layout: article
title: (For me) Mount USB storage on a Raspberry Pi or other Linux system
description: How to mount USB storage on a Raspberry Pi or other Linux device from the terminal.
published: true
---

## Mounting
To mount a USB drive so that the OS can use it, first, you need to know what it is recognised as.
<pre>$ lsblk -f -p
NAME             FSTYPE LABEL  UUID                                 FSAVAIL FSUSE% MOUNTPOINT
/dev/sda                                                                           
└─/dev/sda1      ext4   Music  9ddc2e50-a9a2-4f0b-8ffe-95f6340b6a87    4.6G    31% 
/dev/mmcblk0                                                                       
├─/dev/mmcblk0p1 vfat   boot   4AD7-B4D5                             198.3M    21% /boot
└─/dev/mmcblk0p2 ext4   rootfs 2887d26c-6ae7-449d-9701-c5a4018755b0    8.8G    66% /
</pre>
Find your device, and remember the FSTYPE and NAME.

Then, you will need to make a mount point. You can replace `myusb` with anything you like.
```sudo mkdir /mnt/myusb```


Then, use the following commands, based on what filesystem your USB defice uses. You can tell this from the first command, `lsblk -f -p`. Also, replace `/dev/sda1` and `/mnt/myusb` with what you decided before.
<div class="tg-wrap"><table>
<thead>
  <tr>
    <th>Filesystem</th>
    <th>Commands</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>FAT</td>
    <td><code>sudo mount -t vfat /dev/sda1 /mnt/myusb -o umask=000</code></td>
  </tr>
  <tr>
    <td>EXT4</td>
    <td><code>sudo mount -t ext4 /dev/sda1 /mnt/myusb</code></td>
  </tr>
  <tr>
    <td>NTFS</td>
    <td>For NTFS, you will first need to install <code>ntfs-3g</code>. <code>sudo apt install ntfs-3g</code><br>Then, mount with <code>sudo mount -t ntfs /dev/sda1 /mnt/myusb -o umask=000</code></td>
  </tr>
  <tr>
    <td>exFAT</td>
    <td>First, install <code>exfat-fuse</code>. <code>sudo apt install exfat-fuse</code><br>Then, mount with <code>sudo mount -t exfat /dev/sda1 /mnt/myusb</code></td>
  </tr>
</tbody>
</table></div>
## Unmounting
`sudo umount /mnt/myusb`

