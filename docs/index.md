<img src="https://user-images.githubusercontent.com/96490382/185179903-4cbac04d-d0f7-47e2-b81a-167803205d33.png" width="800"/>

## Internet bonding router with seamless failover using Speedify 
*SmoothWAN* is a customized [OpenWRT](https://openwrt.org/) DIY router for fixed internet bonding setup using  [Speedify](https://speedify.com/), with an emphasis on using an internet browser for easy configuration. 

This project is not affiliated with  [Speedify](https://speedify.com/) or Connectify.

**[WAN](https://en.wikipedia.org/wiki/Wide_area_network)** in a nutshell is an internet connection.

*Supported hardware ordered by performance*

- PC Intel/AMD
- Raspberry Pi 4 / Pi 400
- GL.iNet Flint and Slate AX

*In progress*

- NanoPi R6S
- GL.iNet Flint
- Banana Pi R3
- NanoPi R5S
- Banana Pi R64 

*Use cases*  

- Build a reliable internet access using multiple WANs for seamless failover, lossless and bonded speeds terminating over a single IP address.
- Run a VPN over Speedify: corporate use, bypass captcha/IP-blocking etc.
- Cover all connected devices in a home network when it's not possible or practical to share a WAN and run Speedify on each device e.g: limited mobile data, IoT and multimedia.  
- Significantly lower budget alternative to commonly used enterprise solutions and no off-the-shelf consumer solution to date. (2023)
- Backpack streaming setup by using the webpage for monitoring.

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

 ***
???+ tip "A note for those looking for high speed downloads"
    Speedify is a *bonding* service that terminates your internet access to one IP address using a server. If you need to combine multiple *stable & reliable* internet connections above 300Mbit with no concern on dropouts and slowdowns, a *load balancer* may be more suitable and effecient by using multiple IP addresses eliminating the need for a server, assuming that the majority of the use cases at these speeds involve the use of apps using parallel connections or shared among multiple users.

    Parallel connections example: An app doing a download would split the file in two or more pieces and download each piece simulatenously, the load balancer would then balance each flow to the available internet connections.

    Not all apps split downloads/uploads and thus they may end up using one internet connection only, but 300Mbit is usually sufficient in this case, and the other internet connection will serve other apps/users. Apps that usually download large files will use parallel connections anyways.

    *Bonding* such as Speedify in this use case may be used for reducing issues with services sensitive to IP changes.

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