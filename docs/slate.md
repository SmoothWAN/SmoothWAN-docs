### Ports layout
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1slate.svg"/>

### Troubleshooting

## Slate AX Wi-Fi scan results empty (Only in version 0.99.8)
Disable existing AP/configurations (click Disable buttons) before scanning.  
This issue will be fixed in v1 as well as 802.11s (mesh) support.

## 802.11k/v/s/r Support
GL.iNet wpad full versions are still stripped, force update from OpenWrt official server after installation and reboot:  
`opkg update && opkg remove wpad-openssl && opkg install wpad-openssl --force-overwrite`
