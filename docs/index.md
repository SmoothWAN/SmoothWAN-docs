<h1>Welcome</h1>

![SmoothWAN](https://user-images.githubusercontent.com/96490382/185179903-4cbac04d-d0f7-47e2-b81a-167803205d33.png){: style="max-height:700px;"}

Welcome to SmoothWAN, a small project that aims to provide a reliable and efficient internet bonding solution using Speedify. Our goal is to offer a custom router distribution based on OpenWrt, specifically designed for fixed internet bonding setups. With an emphasis on user-friendly configuration through a web interface, SmoothWAN aims to make internet bonding accessible to users of all technical levels.


## Project Overview

SmoothWAN is an open-source initiative driven by the need for an affordable and feature-rich internet bonding router. Our project aims to address the limitations of existing open-source solutions by incorporating the commercial technology of Speedify. This choice is made based on the lack of affordable and comprehensive open-source alternatives and the desire to provide an accessible solution to a broader audience.

### Key Features

- **Hardware Compatibility:** SmoothWAN supports a range of hardware options, ordered by speed:
  * PC Intel/AMD
  * NanoPi R6S (Work in Progress)
  * NanoPi R5S (Work in Progress)
  * Banana Pi R3 (Untested)
  * Raspberry Pi 4 / Pi 400
  * Banana Pi R64 (Untested)
  * GL.iNet Flint
  * GL.iNet Slate AX

- **Internet Bonding:** SmoothWAN utilizes Speedify's technology to bond two or more internet connections, providing a reliable and high-performance internet access solution. This allows for seamless failover, lossless and aggregated single-flow speeds, and an affordable alternative for areas with limited internet infrastructure.

- **Alternative Solutions:** SmoothWAN also explores alternative self-hosting options, such as Engarde and TinyFEC VPN, providing users with additional choices and flexibility in building their internet bonding setups.


*WebUI preview*
  
<img src="https://user-images.githubusercontent.com/96490382/208723215-92bb40df-c56d-4f82-b597-707aa8e35f7b.gif" width="800"/>


## Project Motives

SmoothWAN's decision to utilize Speedify's commercial solution is motivated by the lack of affordable mixed-usage multi-mode bonding routers that are cost-effective and reliable within the open-source domain. By incorporating Speedify's technology, SmoothWAN aims to bridge this gap and provide a comprehensive internet bonding solution accessible to a wider range of users.

It is important to note that the inclusion of a commercial solution does not imply an endorsement or partnership with Speedify or Connectify. SmoothWAN remains an independent open-source project developed by a dedicated community. The selection of Speedify technology is based on its unique features, performance, and ability to address the specific requirements of internet bonding.

??? note "Project Motives: Commercial Solution Choice and distinguishing features"

    **Note**: These are my own findings and they may not be accurate.

    - Optimization for Various Applications: Speedify goes beyond livestreaming services and provides optimization for a wide range of applications, including SSH and games. This ensures a smooth and enhanced experience across different types of internet activities.

    - Affordability and Server Availability: Speedify leverages publicly shared servers, making it a relatively affordable option. It offers server region selection, allowing users to access region-restricted services and choose from multiple backup public servers for increased reliability.

    - Application-Aware Conditioning: In "Streaming mode," Speedify employs intelligent packet management. Sensitive stream packets, such as those used for VoIP, video calls, streaming, and games, are de-duplicated across bonded connections. This prioritization ensures seamless failover and lossless connectivity. Non-sensitive stream packets are aggregated, maximizing overall speed and efficiency.

    - Advanced Quality Monitoring: Speedify incorporates a sophisticated quality monitoring system for each individual bonded connection. This system assesses factors like jitter, latency, stability, and speed variations over time. By dynamically adapting to network conditions, Speedify prevents unstable connections from significantly affecting the overall performance using "exponential backoff".

    - Automatic Bypass Function: Speedify includes an automatic bypass function that can bypass region or VPN restrictions, enabling access to services like Netflix, even when faced with limitations or blocks.

    - Per WAN VPN Transport Protocols: Speedify supports various VPN transport protocols per individual WAN connection. This flexibility ensures optimal connectivity, especially in environments with strict ISPs or poor middleboxes. Supported protocols include HTTPS (disguised as web browsing), UDP, TCP, and TCP Multiple.

    - TCP Multiple Protocol: The TCP Multiple transport protocol, also known as parallel transfer sockets, is a unique feature of Speedify. It maximizes speed and performance, particularly in scenarios involving high-latency, lossy, geographically distant VPN servers.

    - Adaptive Aggregation and Speed Boost Options: Speedify incorporates intelligent packet aggregation techniques that adapt to asymmetric and heterogeneous WAN bonding scenarios. It allows for quick adaptation on long periods, accommodating cellular and wireless connections with variable speeds. Additionally, Speedify offers options for utilizing WANs solely for speed boosts or as backup connections, providing users with greater control and flexibility.

    - Seamless Configuration Changes: Speedify allows users to switch critical settings such as protocols, modes, and WAN connections without disruption or requiring a system restart. This flexibility simplifies configuration management and enables users to fine-tune their bonding setup according to their specific requirements.
    
    - Non-TCP Bulk Bandwidth: Speedify does not hamper non-TCP bulk bandwidth such as: QUIC, preserving the performance and efficiency of for faster data transfer and improved user experience.

    By combining these unique features, Speedify offers a comprehensive and versatile internet bonding solution, making it a popular choice for users seeking reliable, high-performance connections with seamless failover capabilities.

??? note "Load Balancer vs. Bonding"

    When using a load balancer in a home network, parallel socket performance can be enhanced by distributing the traffic evenly across the available connections. This allows for better utilization of the combined bandwidth and improved download speeds for parallel socket-enabled applications such as downloaders or browsers.

    In the context of failover, network load balancers often employ health checks to monitor the availability and responsiveness of the servers or network resources. If a server or resource becomes unavailable or unresponsive, the load balancer detects this and redirects the incoming traffic to other available servers or resources.

    However, the failover process in network load balancers may not be as seamless and quick as in Speedify. There may be a slight delay or interruption during the failover process, resulting in a temporary loss of connectivity or disrupted network sessions. This is because load balancers typically operate at the network layer and redirect traffic based on protocols and IP addresses.

    Load balancers typically require manual tuning and configuration of quality monitoring parameters to achieve desired results. This process may involve fine-tuning thresholds, adjusting timeout values, and setting up health checks to ensure accurate detection of connection issues.
    
    Load balancers distribute network traffic across multiple servers, but having multiple IP addresses can cause issues. One problem is that requests from the same user can be sent to different servers, disrupting session data. Another issue is that stateful protocols like TCP may not work properly if the client's requests are routed to different servers. To solve these problems, load balancers use "sticky sessions" to ensure requests from the same client go to the same server. Sticky sessions maintain a mapping between the client's IP address and the assigned server, preserving session data and ensuring consistent connections. However, sticky sessions can also have drawbacks like uneven traffic distribution, so their use should be carefully considered.

    In contrast, Speedify offers a different approach by utilizing bonding technology to aggregate the bandwidth of multiple connections into a single, high-performance virtual connection. Speedify is designed to improve both single socket and parallel socket applications by providing seamless failover, dynamic adaptation, and application-aware conditioning.

    Therefore, when considering the difference between a home load balancer and Speedify, it is important to evaluate your specific requirements. If you primarily need load distribution, failover capabilities, and improved parallel socket performance, a load balancer may be a suitable choice. On the other hand, if you are looking for seamless failover, single socket performance improvement, and application-aware optimization, Speedify can be a valuable solution.

    If you have a stable and high-speed connection and the applications you use support parallel socket connections, leveraging single socket aggregation can maximize your internet speed and performance without the need for bonding multiple connections.

    Additionally, when the available internet speed is already high enough that single socket performance is decent and stable, the use of Speedify or bonding may not be necessary.


SmoothWAN's project motives revolve around bridging the gap in open-source solutions, providing an accessible and cost-effective internet bonding router with seamless failover capabilities. While commercial software is employed to achieve these objectives, the project remains independent and not affiliated with Speedify or Connectify. The focus is on fulfilling user needs and providing a reliable and feature-rich solution within the constraints of available resources and existing open-source options.


The page was re-written by **ChatGPT** ![](https://cdn.cdnlogo.com/logos/c/38/ChatGPT.svg){: style="max-height:20px;"}

---

Speedify is a registered trademark of Connectify Inc. Learn more about Speedify [here](https://speedify.com)