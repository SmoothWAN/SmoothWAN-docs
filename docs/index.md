<h1>Welcome</h1>
<img src="https://user-images.githubusercontent.com/96490382/185179903-4cbac04d-d0f7-47e2-b81a-167803205d33.png" width="800"/>
<h2>Internet bonding router with seamless failover using Speedify (primarily)</h2>  
<i>SmoothWAN</i> is a custom [OpenWRT](https://openwrt.org/) router distribution for fixed internet bonding setup using Speedify primarily, with an emphasis on using an internet browser for easy configuration. <br>  
This project is not affiliated with Speedify or Connectify.<br>
Also includes [Engarde]() and [TinyFEC VPN]() as alternatives and self-hosting solutions.<br>

*Supported hardware*

- PC Intel/AMD
- GL.iNet Flint
- GL.iNet Slate AX
- Raspberry Pi 4 / Pi 400
- Banana Pi R64/R3 (soon)

*Use cases*  

- Use [Speedify](https://speedify.com/) to build a reliable internet access with seamless failover, lossless and aggregated single-flow speeds by bonding two or more connections, preferably a combination of wired and wireless with baseline ISP plans as an affordable solution. e.g rural areas, developing countries...
- Cover all connected devices in a home network when it's not possible or practical to share a WAN per each device running Speedify.  
- Use [Engarde](/engarde) as an self-hosting alternative to Speedify's Redundant mode (lossless by duplicating traffic across WANs - no aggregation)
- Use [TinyFEC VPN](/tinyfec) for fixing a lossy unusable internet connection using forward-error-correction (single WAN - self-hosting)
- Low budget alternative to commonly used solutions
- Backpack streaming setup. (RTMP and others are possible in LXC)

*Additional features*

- [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) pre-installed and pre-configured (one-click enable) with password change UI addition
- Dnsmasq DHCP is disabled and replaced with AdGuard Home DHCP. [(revert)](https://smoothwan.com/adg/#due-to-popular-request-and-leak-proof-dns-adgh-is-the-default-dhcp-server)
- Custom Speedify version selection, GUI for built-in custom bypass, and tuning.
- Preset network configuration for various hardware
- VPN PBR pre-configured
- [Tailscale](https://tailscale.com/) installer and pre-configuration
- [ntopng](https://www.ntop.org/products/traffic-analysis/ntop/) (deep-packet-inspection analysis) installer
- One-click cloud-init script for setting up Engarde & TinyFEC VPN in cloud
- [BitTorrent detection log](/tips/#identifying-client-using-p2p-or-bittorrent) showing client IP address as the source
- Per-client (LAN) bandwidth limiter (EQoS)

*Typical setup*  
<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN-web/main/smoothwan-illust.drawio.svg" width="600"/>

*WebUI preview*
  
<img src="https://user-images.githubusercontent.com/96490382/208723215-92bb40df-c56d-4f82-b597-707aa8e35f7b.gif" width="800"/>

 ***
*Wiki under construction 👷*
###On Speedify being primary
 
As of (2023), I could not find an affordable mixed usage multi-mode bonding software and a service that is cost effective nor a reliable OSS solution.  

??? note "More details about Speedify - Wishlist for other solutions"
 
    **Note:** These are my own findings and they may not be accurate.

    - Includes optimization for non-livestreaming services in addition to livestreaming, e.g SSH, games etc. 
    - Relatively affordable due to publicly shared servers. 
    - Server region selection for region restricted services and multiple backup public servers. 
    - Application aware conditioning in "Streaming mode": sensitive streams packets (when detected) are duplicated across WANs and prioritized for VoIP, video calls, streaming, and games for seamless failover and lossless connectivity even when combining lossy WANs. While non-sensitive streams packets are aggregated across WANs for the speed of the total combined WANs, and bulk downloads using single sockets are aggregated. Sensitive streams are also aggregated with high quality sources. 
    - Advanced quality monitoring: per WAN quality rating system that's based on jitter, latency, stability, and speed variations over a period of time to prevent an unstable WAN from impacting total aggregation performance. e.g WAN resume and suspend delay is increased on multiple failures, poor connections will be removed from aggregation and used for backup etc. 
    - Automatic bypass function for region/VPN restricted services. e.g Netflix 
    - Per WAN VPN transport protocols for optimal connectivity when used with strict ISPs or poor middleboxes, used protocols: HTTPS(disguises as web browsing), UDP, TCP, TCP Multiple. 
    - "TCP Multiple" transport protocol as known as parallel transfer sockets allows maximum speed to be achieved on high latency, lossy, and far region VPN servers (with loss based CCA host settings and out-of-order packets). 
    - Quick packet aggregation weighing for largely asymmetric and heterogenous WANs bonding while slowly adapting on long periods when using cellular/wireless with variable speeds. 
    - Low out of order packet delivery on aggregation, needed for single socket TCP connection performance at the cost of minor latency increase. 
    - Options for using a WAN for speed boosts only with adjustable threshold (advanced - CLI) and backup only mode. 
    - Switching critical settings such as protocols, modes, and adding or removing WANs without disruption or requiring a restart. 
    - Maintains low TCP-over-TCP overhead relative to other VPNs. 
