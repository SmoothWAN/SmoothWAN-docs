<h1>Welcome</h1>
<img src="https://user-images.githubusercontent.com/96490382/185179903-4cbac04d-d0f7-47e2-b81a-167803205d33.png" width="800"/>
<h2>Internet bonding router with seamless failover using Speedify</h2>
<i>SmoothWAN</i> is a custom [OpenWRT](https://openwrt.org/) router distribution for fixed internet bonding setup using Speedify, with an emphasis on using an internet browser for easy configuration. <br>  
This project is not affiliated with Speedify or Connectify.<br>
<br>
<h3>Use cases: </h3>
- Build a reliable internet access with seamless failover, lossless and usable single-flow speeds by bonding two or more connections, preferably a combination of wired and wireless with baseline ISP plans as an affordable solution. e.g rural areas, developing countries...
- Cover all connected devices in a home network when it's not possible or practical to share a WAN per each device running Speedify.  
- Low budget alternative to commonly used solutions
- Backpack streaming setup. (RTMP and others in LXC containers)
  
<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN-web/main/smoothwan-illust.drawio.svg" width="600"/> <br>  
<sub>[- More info on Pi's Wi-Fi setup](https://github.com/TalalMash/SmoothWAN/discussions/18#discussioncomment-2521688)<br>- Slate AX/Flint is easier to setup with no extra hardware.</sub>  
  
Wiki is under development.

 ***

<h3>Motives</h3>
As of (2022) I couldn't find an affordable mixed usage multi-mode bonding software and a service that is cost effective, nor a reliable OSS solution.
<details> 
<summary>More details</summary>
<b>Note:</b> These are my own findings/review and they are not accurate. <br>
<br>
- Includes optimization for non-livestreaming services in addition to livestreaming, e.g SSH, games etc. <br>
- Relatively affordable due to publicly shared servers. <br>
- Server region selection for region restricted services and multiple backup public servers. <br>
- Application aware conditioning in "Streaming mode": sensitive streams packets (when detected) are duplicated across WANs and prioritized for VoIP, video calls, streaming, and games for seamless failover and lossless connectivity even when combining lossy WANs. While non-sensitive streams packets are aggregated across WANs for the speed of the total combined WANs, and bulk downloads using single sockets are aggregated. Sensitive streams are also aggregated with high quality sources. <br>
- Advanced quality monitoring: per WAN quality rating system that's based on jitter, latency, stability, and speed variations over a period of time to prevent an unstable WAN from impacting total aggregation performance. e.g WAN resume and suspend delay is increased on multiple failures, poor connections will be removed from aggregation and used for backup etc. <br>
- Automatic bypass function for region/VPN restricted services. e.g Netflix <br>
- Per WAN VPN transport protocols for optimal connectivity when used with strict ISPs or poor middleboxes, used protocols: HTTPS(disguises as web browsing), UDP, TCP, TCP Multiple. <br>
- "TCP Multiple" transport protocol as known as parallel transfer sockets allows maximum speed to be achieved on high latency, lossy, and far region VPN servers (with loss based CCA host settings and out-of-order packets). <br>
- Quick packet aggregation weighing for largely asymmetric and heterogenous WANs bonding while slowly adapting on long periods when using cellular/wireless with variable speeds. <br>
- Low out of order packet delivery on aggregation, needed for single socket TCP connection performance at the cost of minor latency increase. <br>
- Options for using a WAN for speed boosts only with adjustable threshold (advanced - CLI) and backup only mode. <br>
- Switching critical settings such as protocols, modes, and adding or removing WANs without disruption or requiring a restart. <br>
- Maintains low TCP-over-TCP overhead relative to other VPNs. <br>
  
</details>
