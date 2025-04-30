## MACVLAN Setup

<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN-web/main/macvlan.svg" >

### Device Details

- **Device type**: MACVLAN
- **Base device**: br-lan
- **Mode**: Bridge
- **Device name**: Any name  

### Notes

- MACVLAN is not a replacement for VLAN, use VLAN whenever possible.
- Some modems, especially ISP-supplied ones, may cause rogue DHCP scenarios. They **reject** DHCP messages, but the server remains **on** for internal reasons. MACVLAN is not suitable in this case.
- MACVLAN is used for budget setups.
- Do not enable software offload in the firewall when using MACVLAN, as it may affect the ARP table.
- Some white-label brand 100-Mbit switches may perform poorly with multiple addresses from the same port due to limited switching fabric. Use a cheap gigabit switch.
- Disable IPv6 on all modems.

### Diagnostics

#### Simple Check

- Microsoft Rogue DHCP Checker should show one DHCP server:

  <img src="https://user-images.githubusercontent.com/96490382/167432465-d0816b39-ddb1-43fd-9925-916f05284f67.png" style="border:6px solid #d2ccf1;max-height:300px"/>

#### Advanced Check

- For Linux/MacOS: Disconnect SmoothWAN and the client from the network. Use Wireshark to listen on the broadcast, reconnect the client to the network, and observe any DHCP messages. There should only be a single source.
