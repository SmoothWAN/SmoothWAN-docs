**Access to devices connected to your home network remotely (e.g old security system, automation, NAS)**
## Setup after installing Speedify or setting up a WAN
<img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/1.webp"/>  

Log result should be similar to:  
<img src="https://user-images.githubusercontent.com/96490382/156564555-812292a4-2932-47f4-b2bb-10f652cd2e01.png"/>  
Visit: http://172.17.17.2:8088/ to login/signup to Tailscale.  
  
After a successful login, visit: https://login.tailscale.com/admin/machines and toggle settings as the following:  
<img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/3.webp" width="600"/>  
<img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/4.webp"/>  
<img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-tailscaleconf/root/www/luci-static/resources/view/tailscaleconf/5.webp" width="600"/>  

***

### After installation
* You will be able to access your local (LAN) devices from range 172.17.17.0 to 172.17.17.255 remotely on any device that has Tailscale running and connected to the same account.
* You can enable "exit node" option in dashboard to use your home networking internet on the go. E.g Bypass Netflix location / account sharing restrictions.