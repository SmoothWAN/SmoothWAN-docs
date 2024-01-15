
## Common issues

### Unable to save changes - "Restart Speedify" visible - "Login button" invisible

Make sure to add the web address to your ad-blocker whitelist.  
Speedify may have crashed or stopped working.  

### Speedify did not detect internet/WAN not visible

An interface name that starts with "br-" prefix is ignored.  

### Speedify bypass (domain based) not working with PPPoE interfaces

As of Speedify version 12.6, Speedify seems to use the gateway of each WAN as the DNS resolver for bypass.  
This may have been fixed in future versions.  
You can use VPN Policy Based Routing as an alternative.  

### Speedify installer issues

- Wait around a minute on fresh start or after plugging in single WAN to synchronize date/time  
- Reboot after first boot or check the date/time in System  
- Use the best quality WAN during installation  

### Internet connectivity issue on Intel/AMD build

Depending on the hardware and how interfaces are brought up, OpenWRT may create a default WAN interface on first boot as `WAN` and `WAN_6`.  
Delete these interfaces in _Network -> Interfaces_ and restart.  

