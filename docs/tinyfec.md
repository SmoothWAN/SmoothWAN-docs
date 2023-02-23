
- [TinyFEC VPN (by wangyu-)](https://github.com/wangyu-/tinyfecVPN): A VPN Designed for Lossy Links, with built-in Forward Error Correction (FEC). Improves your network quality on a high-latency lossy link.
- Corrects a single internet source (WAN) only.
- Improves network speed on lossy internet connections by sending redundant packets.
- Low goodput on high throughput connections due to the redundancy, however dynamic adjustment is tuned.
- Dynamic adjustment increases/decreases redundant packets on packet loss levels to reduce bandwidth waste.
- Latency variations and high latency is a side effect of correcting packet loss.
- Significant performance improvements are noticeable with TCP connections and DNS queries.
- Processing intensive, requiring 3.0Ghz Intel/AMD router and server for >100Mbit speeds.

***

Server setup using Vultr as an example with cloud-init:  
Visit <a href='https://my.vultr.com/'>https://my.vultr.com</a> and login/signup, then follow the arrows:
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/1.webp" style="max-height:300px"/><br>
Choose Cloud Compute
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/2.webp" style="max-height:300px"/><br>
Choose High Frequency (since TinyFEC VPN is single threaded)
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/3.webp" style="max-height:300px"/><br>
Choose latest Ubuntu and the nearest location, example selects European region
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/4.webp" style="max-height:300px"/><br>
Choose a plan according to bandwidth to be used, not hardware resources
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/5.webp" style="max-height:300px"/><br>
Copy and paste the content below then locate and change the password in the pasted content:
<iframe style="border:6px solid #d2ccf1;" src="/assets/tinyfec/user-data.txt"></iframe>
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/6.webp" style="max-height:300px"/><br>
Wait few minutes till the IP address appears, and note it down
You can wait few minutes or monitor progress by clicking View Console
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/7.webp" style="max-height:300px"/><br>
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/8.webp" style="max-height:300px"/><br>
Copy the noted IP address & password in the configuration tab of this page and check Enable, Save & Apply
<img style="border:6px solid #d2ccf1;" src="/assets/tinyfec/9.webp" style="max-height:300px"/><br>
All done! Check your IP address at ping.eu,speedtest.net,etc... to check if it's working correctly, it should match the IP address of your server.
<hr>
<h3>Notes:</h3>

- The server is setup to forward all ports to your SmoothWAN appliance/router.
- Modern implementation UPnP is automatically configured and enabled for automatic port forwarding.
- You can also forward ports in VPN -> VPN Port Forwarding.
- Changing password is done by simply changing the cloud-init field and doing a server reinstall.
- VPN via server providers is (usually) not log-free as it's used for abuse monitoring, privacy may be equivalent to a direct ISP connection.
- You can use other providers, Vultr is used as it's the easiest, there is no affiliation.
- You may need to modify the cloud-init script for some providers, it's limited to KVM/Virt machines only.
- SSH on the server is disabled by default.
