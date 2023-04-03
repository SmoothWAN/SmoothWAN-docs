### Bypass a client to a WAN or for P2P torrent activity

1. Make sure your client is set to static by visiting _Network -> DHCP and DNS -> Static Leases_ then click _Add_ (assuming the IP in this example is 172.17.17.128)
2. Head over to _VPN -> VPN Policy Routing_ or *Services* -> *Policy Routing* 
3. Click _Enable_ and _Start_
4. In Policies add your client IP in the `Local Addresses / devices` field and add your LAN subnet in the `Remote addresses / domains`, and choose your WAN.
5. You can also use MAC addresses, easier to manage IPv6.
6. Click *Save & Apply*, reconnect Speedify to clear P2P detection (toggle power switch), and reconnect your client to obtain the static IP.

### Split-tunneling for leak-proof bypass

In rare cases where Speedify adapter restarts, [PBR](https://docs.openwrt.melmac.net/pbr/) will automatically re-apply the tables leading to potential leak with certain P2P programs.  

The solution is to use routing tables, note that this will also act as a kill-switch for the particular WAN when Speedify is down, meaning that the non-split-tunneled clients won't be able to use it when Speedify is down, the next connected WAN will be used instead unless it's also in split-tunneling mode. Clients that are bypassed are uninterrupted.

As an added feature, this ensures that split-tunneled active connections won't break when PBR/Speedify restarts.  

Follow these steps to bypass a static IP client to a specific WAN:

1. Head to *Network* -> *Interfaces* -> *Edit* button next to the WAN to be used.
2. *Advanced Settings* -> *Override IPv4 routing table*, select one of the `BYP` tables, there are 10 presets. When split-tunneling other WANs do not use the same table.
3. *Save* then head to *Network* -> *Routing* -> *IPv4 Rules* -> *Add*
4. Set *Incoming interface* to `lan` and *source* to your client IP address.
5. Select the `BYP` you chose earlier in *Table* and click *Save and Apply*.
6. Done! For IPv6 users, ULA is disabled, link-local is mostly persistent you add the same rule in *IPv6 Rules* tab.