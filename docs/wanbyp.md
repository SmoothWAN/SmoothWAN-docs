### Bypass a client to a WAN or for P2P torrent activity
1. Make sure your client is set to static by visiting _Network -> DHCP and DNS -> Static Leases_ then click _Add_ (assuming the IP in this example is 172.17.17.128)
2. Head over to _VPN -> VPN Policy Routing_
3. Click _Enable_ and _Start_
4. In Policies add your client IP in the `Local Addresses / devices` field and add your LAN subnet in the `Remote addresses / domains` **with a** `!` **prefix**, and choose your WAN:
![image](https://user-images.githubusercontent.com/96490382/198855901-73a913ab-74a0-40eb-8033-43b75189ebc3.png)
Ignore the red dialog warning
5. Click Save & Apply, reconnect Speedify to clear P2P detection (toggle power switch), and reconnect your client to obtain the static IP.

Note:
This can also be used to bypass devices/ports to a specific WAN.