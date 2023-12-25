## Description
Install SmoothWAN to an internal (non-removable) disk such as a laptop.

Warning: All data will be lost.

## Instructions
After running SmoothWAN with the [Quick Setup](rpi4.md) instructions using a USB flash drive with a working internet connection, log-in to the Web UI:
    
1. Enter `lsblk` in Services -> Terminal after logging in to view connected disks.
2. Note down the internal drive path, e.g `/dev/sda` as an example used in the next step.
```
sda      8:0    0    320G  0 disk <-- Ignore the numbered partitions below
├─sda1   8:1    0     1M  0 part
├─sda2   8:2    0   513M  0 part
└─sda3   8:3    0  127.5G  0 part
...
```
3. Download the image straight to the drive:
```
curl -L https://github.com/SmoothWAN/SmoothWAN/releases/download/0.99.9HF5/SmoothWAN-0.99.9HF5-PC-EFI-AMD64-DiskImage-or-WebUI.img.gz | gzip -d -c | dd bs=4M of=/dev/sda conv=fsync
```
4. Power off, unplug the flash drive, then power on, your PC will restart twice in order to automatically expand and use the entire internal drive storage.