## Split Tunneling

Set your DHCP server to provide a static IP address to the target client. (Can be skipped if set on client)

*Network* -> *DHCP and DNS* -> *Static Leases* -> *Add* button and choose the MAC address & specify IP address.

Follow these steps to bypass a static IP client to a specific WAN:

1. Head to *Network* -> *Interfaces* -> *Edit* button next to the WAN to be used.
2. *Advanced Settings* -> *Override IPv4 routing table*, select one of the `BYP` tables, there are 10 presets. When split-tunneling other WANs do not use the same table.
3. *Save* then head to *Network* -> *Routing* -> *IPv4 Rules* -> *Add*
4. Set *Incoming interface* to `lan` and *source* to your client IP address. e.g `172.17.17.100/32`
5. Select the `BYP` you chose earlier in *Table* and click *Save and Apply*.
6. Done! For IPv6 users, you will have to use MAC addresses instead (TODO: Guide).

Never share the same routing table number `BYP` with other WANs/VPNs.

### Bypass a range of IP addresses

Use CIDR calculators such as https://www.ipaddressguide.com/cidr  
Example: using `172.17.17.32/27` will bypass clients with IP addresses between `172.17.17.32` and `172.17.17.63`  
`/32` CIDR such as in the previous examples equals to one IP address.