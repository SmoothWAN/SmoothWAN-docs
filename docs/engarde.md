- [Engarde (by porech)](https://github.com/porech/engarde): A go network utility to create a reliable IP tunnel over multiple connections.
- Duplicate traffic over multiple internet connections using Wireguard.
- A self-hosting alternative to Speedify's Redundant mode, without bufferbloat.
- Offers ~1ms lossless failover duration, and low latency over lossy connections.
- No aggregation, speed of the fastest WAN is the result bandwidth throughput.
- No data consumption reduction on slower WANs, since there is no quality monitoring, hence the low-latency feature compared to Speedify.
- Processing intensive, requiring 3.0Ghz Intel/AMD router and server for >100Mbit speeds.

***

Server setup using Vultr as an example with cloud-init:</h4>
Visit <a href='https://my.vultr.com/'>https://my.vultr.com</a> and login/signup, then follow the arrows:
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/1.webp" style="max-height:300px"/><br>
Choose Cloud Compute
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/2.webp" style="max-height:300px"/><br>
Choose High Frequency (since Engarde is single threaded)
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/3.webp" style="max-height:300px"/><br>
Choose latest Ubuntu and the nearest location, example selects European region
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/4.webp" style="max-height:300px"/><br>
Choose a plan according to bandwidth to be used, not hardware resources
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/5.webp" style="max-height:300px"/><br>
Copy and paste the content below then locate and change the password in the pasted content:
<iframe style="border:6px solid #d2ccf1;" src="/assets/engarde/user-data.txt"></iframe>
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/6.webp" style="max-height:300px"/><br>
Wait few minutes till the IP address appears, and note it down  
You can wait few minutes or monitor progress by clicking View Console
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/7.webp" style="max-height:300px"/><br>
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/8.webp" style="max-height:300px"/><br>
Copy the noted IP address & password in the configuration tab of this page and check Enable, Save & Apply
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/9.webp" style="max-height:300px"/><br>
Engarde will automatically detect connectivty via any interface in Active Interfaces section and use it!
<img style="border:6px solid #d2ccf1;" src="/assets/engarde/10.webp" style="max-height:300px"/><br>
All done! Note that the example shows only one WAN plugged in.  
Check your IP address at ping.eu,speedtest.net,etc... to check if it's working correctly, it should match the IP address of your server.
<hr>
<h3>Notes:</h3>

- The server is setup to forward all ports to your SmoothWAN appliance/router.<br>
- Modern implementation UPnP is automatically configured and enabled for automatic port forwarding.<br>
- You can also forward ports in VPN -> VPN Port Forwarding.<br>
- Changing password is done by simply changing the cloud-init field and doing a server reinstall.<br>
- VPN via server providers is (usually) not log-free as it's used for abuse monitoring, privacy may be equivalent to a direct ISP connection.<br>
- You can use other providers, Vultr is used as it's the easiest, there is no affiliation.<br>
- You may need to modify the cloud-init script for some providers, it's limited to KVM/Virt machines only.<br>
- SSH on the server is disabled by default.<br>
