[-> Upcoming features <-](https://github.com/TalalMash/SmoothWAN/projects/1)  
  
- Speedify installer, auto-update and version selection
- Preset network configuration for various hardware
- Data caps and consumption in Speedify are persistent due to the previously mentioned features
- Bypass Speedify with selective WAN for local devices/ports/domains using a PBR and/or Speedify's internal bypass with a LuCI app for adaptive WAN selection using data caps and other conditions
- [AdGuard Home](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-AdGuard-Home-(GL.iNet)) pre-installed and pre-configured (one-click enable) with password change UI addition
- [Tailscale installer](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-Tailscale) for easy remote access to connected devices in your home network  
- [PnP mini-display support](https://github.com/TalalMash/SmoothWAN/wiki/Setting-up-OLED-display-for-stats-(RPi4)) for displaying Speedify info, typically used for backpack streaming
- Per platform OpenWRT optimizations and pre-configured LuCI apps
- Extended diagnostics including Pi [vcgencmd]() tool in-browser and independent WAN speed test
- External low-res display indicator and battery monitoring (Pi)
- Bypass tethering restrictions by default (TTL)
- Download logs for various apps from browser for easy diagnosis
- VPN PBR pre-configured
- [Engarde](/engarde) as an self-hosting alternative to Speedify's Redundant mode (lossless by duplicating traffic across WANs - no aggregation)
- [TinyFEC VPN](/tinyfec) for fixing a lossy unusable internet connection using forward-error-correction (single WAN - self-hosting)
- One-click cloud-init script for setting up Engarde & TinyFEC VPN in cloud
- BitTorrent detection log showing client IP address as the source
- Per-client (LAN) bandwidth limiter (EQoS)
