### Port Layout
Credits to **sqlazer** for sending one for testing and support
![](assets/slateports.webp)

### Troubleshooting

## Slate AX Wi-Fi scan results empty (Only in version 0.99.8)
Disable existing AP/configurations (click Disable buttons) before scanning.  
This issue was fixed in v0.99.

## 802.11k/v/s/r Support
GL.iNet `wpad` is stripped, force update from OpenWrt official server after installation and reboot:  
`opkg update && opkg remove wpad-openssl && opkg install wpad-openssl --force-overwrite`
