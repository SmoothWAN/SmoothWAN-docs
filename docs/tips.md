
### Identifying client using P2P or BitTorrent

![](/assets/p2p.jpg)

### Cannot connect to Wi-Fi 2.4Ghz client (Wireless WAN)

Check for connected USB 3.0+ devices as it's a [common issue with 2.4Ghz Wi-Fi](https://en.wikipedia.org/wiki/USB_3.0#Issues)

### Quick VLAN setup

Assuming ISP modem is plugged at trunk #1 on the managed switch:  
*Network* -> *Interfaces* -> *Devices* -> *Add device configuration* 

(change _Device Name_ for a more friendly name to appear in Speedify UI) 

<img src="https://user-images.githubusercontent.com/96490382/166711545-70232fd3-dc40-4f06-9a05-4d6fb6697d89.png" width=500 />  

*Network* -> *Interfaces* -> *Add new interface*   

<img src="https://user-images.githubusercontent.com/96490382/166711876-88b897a8-4439-4c77-b3eb-0b333be3a869.png" width=500 />  

Set Firewall zone to RED, and gateway metric to `200` or more.

### Reduce bufferbloat - Gaming (less bandwidth gain)
* Set one WAN as "Primary", preferably the landline or the lowest latency, others as "Secondary".    
* Set transport mode to UDP, and rate limit each to 70% of max speed.  
* Optionally set mode to redundant.
* Engarde may perform better than Speedify in this case but requires limiting the speed per WAN via SQM which may hinder throughput.

*Ping (ICMP) is not a good measure, in "Streaming mode" detected flows are optimized and use a different path (redundant - low buffer). Use in-game latency indicators.*   
*Speedify UDP mode is sensitive to software & hardware interrupts under load, requires a PC instead of Slate/Flint >30Mbit or Pi4 >80Mbit to control bufferbloat to a minimum (~10%)*

### Hide interface or WAN from Speedify

Rename interface to start with "br-"

### Check downloaded image integrity
You can use [in-browser tools](https://emn178.github.io/online-tools/sha256_checksum.html) to check the file for errors, the calculated sum is in `sha256.*` file in the Releases section.  
### Persistent statistics (graphs) on power cycles (version 0.99.8 and below)
Visit _Statistics->Setup_ and in _RRDtool output plugin_ set _Storage Directory_ to `/etc/rrd`  
High endurance or MLC SD card is recommended but not required
