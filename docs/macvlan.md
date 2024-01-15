<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN-web/main/macvlan.svg" >  
  
- Device type: MACVLAN
- Base device: br-lan
- Mode: Bridge
- Device name: any name  

**Notes:** <br>
- **MACVLAN is not a replacement for VLAN, use VLAN whenever possible**.  
- Few modems especially ISP supplied will cause rogue DHCP scenario. They **reject** DHCP messages but the server is still **on** for internal reasons. MACVLAN is not suitable in this case.  
- MACVLAN is used for budget/fleet setups.  
- Do not enable software offload in firewall when using MACVLAN as it may affect the ARP table.  
- Some no-name 100-Mbit switches will perform poorly with multiple addresses from the same port due to limited switching fabric. Use a gigabit switch.  
- Disable IPv6 on all modems.  

**Diagnostics:**  

* (Simple) Microsoft Rogue DHCP Checker should show one DHCP server:  

<img src="https://user-images.githubusercontent.com/96490382/167432465-d0816b39-ddb1-43fd-9925-916f05284f67.png" style="border:6px solid #d2ccf1;max-height:300px"/>    

  
* (Advanced) For Linux/MacOS, disconnect SmoothWAN, disconnect client from network, listen on broadcast with Wireshark, connect client to network, observe for any DHCP message, there should be a single source.
