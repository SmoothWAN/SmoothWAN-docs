### Port Layout
![](assets/flintports.png)

## 802.11k/v/s/r Support
GL.iNet `wpad` is stripped, force update from OpenWrt official server after installation and reboot:  
`opkg update && opkg remove wpad-openssl && opkg install wpad-openssl --force-overwrite`
