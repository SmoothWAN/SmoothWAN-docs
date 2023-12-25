<img src="https://user-images.githubusercontent.com/96490382/185179903-4cbac04d-d0f7-47e2-b81a-167803205d33.png" width="800"/>

## Internet bonding router with seamless failover using Speedify 
*SmoothWAN* is a customized [OpenWRT](https://openwrt.org/) based DIY router for quick internet bonding setup using  [Speedify](https://speedify.com/), with an emphasis on using an internet browser for easy configuration. 

This project is not affiliated with  [Speedify](https://speedify.com/) or Connectify.

*[WAN](https://en.wikipedia.org/wiki/Wide_area_network) is an internet connection.*

*Supported hardware ordered by performance*

- PC Intel/AMD
- Raspberry Pi 4 / Pi 400
- GL.iNet Flint and Slate AX

*Use cases*  

- Build a reliable internet access using multiple WANs for seamless failover, lossless and bonded speeds terminating over a single IP address.
- Run a VPN over Speedify: corporate use, bypass captcha/IP-blocking etc.
- Cover all connected devices in a home network when it's not possible or practical to share a WAN and run Speedify on each device e.g: limited mobile data, IoT and multimedia.

*Extras*

- Use [Engarde](https://github.com/porech/engarde) for self-hosting alternative to Speedify's Redundant mode.
- Use [TinyFEC VPN](https://github.com/wangyu-/tinyfecVPN) for fixing a lossy unusable internet connection using forward-error-correction at a speed cost while maintaining low latency.
- Many more in [features](https://smoothwan.com/features/)
***
*Typical setup*  
<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN-web/main/smoothwan-illust.drawio.svg" width="600"/>

***

*WebUI preview*
  
<img src="https://user-images.githubusercontent.com/96490382/208723215-92bb40df-c56d-4f82-b597-707aa8e35f7b.gif" width="800"/>

???+ abstract "Project motives"
 
    **Note:** These are my own findings on Speedify in technical terms and they are not accurate.

    - Mixed usage is considered other than livestreaming (browsing, games, low latency video calls etc).
    - Relatively affordable (due to publicly shared servers). 
    - Region selection for geo restricted services and multiple backup public servers in the same region. 
    - Application aware bonding in "Streaming mode": sensitive streams packets (when detected) are duplicated across WANs and prioritized for VoIP, video calls, streaming, and games for seamless failover and lossless connectivity even when combining lossy WANs, total speed ends up with the fastest WAN. While non-sensitive streams packets are aggregated across WANs for the speed of the total combined WANs. Sensitive streams are also aggregated on good quality WANs. 
    - Exponential backoff to prevent an unstable or slow WAN from impacting total aggregation performance. 
    - Bypass service that is automatically updated for region or VPN restricted services. e.g Netflix 
    - Per WAN transport protocols for optimal connectivity when used with strict ISPs and poor firewalls, used protocols: HTTPS(disguises as web browsing), UDP, TCP, TCP Multiple. 
    - Parallel TCP transfer sockets allows maximum speed to be achieved on high latency, lossy, and far bonding servers. (Similar to single TCP with BBR CCA)
    - Options for using a WAN for speed boosts only (Secondary), with adjustable threshold (advanced - CLI) and backup only mode. 
    - Switching critical settings such as protocols, modes, and adding or removing WANs without disruption or requiring a restart. 
    - Low TCP-over-TCP overhead, UDP-over-TCP is not strictly ordered.