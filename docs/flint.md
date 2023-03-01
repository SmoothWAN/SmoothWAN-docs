### Port layout is work in progress 
Current 0.99.9 is untested!  
I do not own the hardware, post your feedback in the issues page.  
[Ticket #69](https://github.com/TalalMash/SmoothWAN/issues/69)  
![](assets/flintports.png)

## 802.11k/v/s/r Support
GL.iNet wpad full versions are still stripped, force update from OpenWrt official server after installation and reboot:  
`opkg update && opkg remove wpad-wolfssl && opkg install wpad-wolfssl --force-overwrite`
