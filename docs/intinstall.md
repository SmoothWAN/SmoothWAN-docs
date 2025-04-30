Install SmoothWAN to an internal (non-removable) disk, such as a laptop hard drive.

!!! warning
    **All data on the selected internal drive will be permanently lost. Proceed with caution.**

---

After running SmoothWAN using the [Quick Setup](rpi4.md) instructions with a USB flash drive and an active internet connection, follow these steps to install it on an internal drive:

1. Log in to the Web UI and open **Services → Terminal**.

2. Run the following command to list all connected disks:
    ```
    lsblk
    ```

3. Identify your internal drive (e.g., `/dev/sda`) in the output.  
   **Ignore** the numbered partitions (`sda1`, `sda2`, etc.) and note only the main disk path.

    Example:
    ```
    sda      8:0    0    320G  0 disk   <-- Use this
    ├─sda1   8:1    0      1M  0 part
    ├─sda2   8:2    0    513M  0 part
    └─sda3   8:3    0  127.5G  0 part
    ```

4. Flash the internal drive with the SmoothWAN image (replace with latest version):

    ```
    curl -L https://github.com/SmoothWAN/SmoothWAN/releases/download/0.99.9HF5/SmoothWAN-0.99.9HF5-PC-EFI-AMD64-DiskImage-or-WebUI.img.gz | gzip -d -c | dd bs=4M of=/dev/sda conv=fsync
    ```

5. Once complete, power off the device, unplug the flash drive, and power on again.  
   The system will automatically reboot twice to expand and use the full internal storage.
