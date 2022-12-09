[>Upcoming features<](https://github.com/TalalMash/SmoothWAN/projects/1)  

-  USB port agnostic naming and configuration for portable setups using MAC-addr for USB Ethernet adapters, 4G USB dongles* (RNDIS, Pi/PC)  
-  Preset configuration for USB Ethernet adapters and tethering devices for plug and play (Pi/PC) with interface renaming. (Android tehtering, iOS in version 1.0) 
-  Data caps and consumption in Speedify are persistent due to the features mentioned previously respectively
-  Bypass Speedify with selective WAN for local devices/ports/domains using a PBR and/or Speedify's internal bypass with a LuCI app for adaptive WAN selection using data caps and other conditions.
-  [Pi-hole installer](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-Pi-hole) for local home network adblocking (Pi/PC)  
-  [AdGuard Home](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-AdGuard-Home-(GL.iNet)) pre-installed for low memory GL.iNet devices
-  [Tailscale installer](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-Tailscale) for easy remote access to connected devices in your home network  
-  [PnP mini-display support](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-OLED-display-for-stats-(RPi4)) for displaying Speedify info, typically used for backpack streaming
- Per platform OpenWRT optimizations and preconfigured LuCI apps
- Client bandwidth monitoring using [iptmon]()
- Extended diagnostics including Pi [vcgencmd] tool in-browser and independent WAN speed test
- External low-res display support and battery monitoring (Pi)
- Bypass tethering restrictions by default (TTL)
- Download logs for various apps from browser for easy diagnosis
- Per-platfrom optimizations
