# Remote Access to Devices on Your Home Network

Easily access devices connected to your home network remotely, such as an old security system, home automation devices, or a NAS.

## Setup After Installing Speedify or Setting Up a WAN

1. Open the Tailscale configuration page.
   <img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/1.webp" style="border:6px solid #d2ccf1;max-height:300px"/>  

2. Verify the log results. They should look similar to the following:  
   <img src="https://user-images.githubusercontent.com/96490382/156564555-812292a4-2932-47f4-b2bb-10f652cd2e01.png" style="border:6px solid #d2ccf1;max-height:300px"/>  

3. Visit [http://172.17.17.2:8088/](http://172.17.17.2:8088/) to log in or sign up for Tailscale.

4. After successfully logging in, go to the [Tailscale Admin Page](https://login.tailscale.com/admin/machines) and adjust the settings as shown below:  
   <img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/3.webp" style="border:6px solid #d2ccf1;max-height:300px"/>  
   <img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/4.webp" style="border:6px solid #d2ccf1;max-height:300px"/>  
   <img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/5.webp" style="border:6px solid #d2ccf1;max-height:300px"/>  

---

## After Installation

- You will be able to access your local (LAN) devices in the range `172.17.17.0` to `172.17.17.255` remotely from any device running Tailscale and connected to the same account.
- You can enable the "Exit Node" option in the Tailscale dashboard to use your home network's internet while on the go. This can help bypass location-based restrictions, such as Netflix account sharing limitations.