<h1>Work in progress</h1>
<h2>I'm currently collecting frequently asked questions...</h2>

## Common issues
### Speedify did not detect internet/WAN not visible
An interface name that starts with "br-" prefix is ignored.

### Speedify bypass (domain based) not working with PPPoE interfaces
As of 12.6, Speedify seems to use the gateway of each WAN as the DNS resolve for bypass, this issue is common with PPPoE and providers offering alternate DNS servers   
No workarounds yet.  
Use VPN Policy Based Routing in the meantime.

### Speedify installer issues
Possible remedies:
- Wait around a minute on fresh start or after plugging in single WAN to synchronize date/time
- Use the best quality WAN during installation
- Reboot after first boot
- Submit an issue.

### Internet connectivity issue on PC/x86 build
Depending on the hardware and how interfaces are brought up, OpenWRT may create a default WAN interface on first boot as `WAN` and `WAN_6`.
Delete these interfaces in _Network -> Interfaces_ and restart. (Fixed in next release)

### SQM QoS affecting performance
Unequal link bonding adds artificial latency and buffer, it's recommended to disable SQM or add 20% of total aggregated speed in shaper for QoS related functions only such as per-host distribution, diffserv, and etc.
