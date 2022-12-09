## Setup after installing Speedify or setting up a WAN  
1. Visit `http://172.17.17.2:3000/install.html` (replace `172.17.17.2` if you changed LAN IP address)
2. Follow the setup guide
3. Fill the first `Port` field with `3000`, and the second field with `3001`, click next.
4. Set the username and password to your preference, click Next, ignore "Configure your devices" section
5. Go to `Settings -> DNS Settings`, replace Upstream servers with `10.202.0.1` and `8.8.8.8` with a new line in-between.
6. Login to SmoothWAN WebUI, go to `Network -> DHCP and DNS`
7. Edit `DNS Forwardings:`, enter `127.0.0.1#3001`, click `+`
8. Click `Save & Apply`, restart SmoothWAN
9. Done! Manage AdGuard Home at `http://172.17.17.2:3000`