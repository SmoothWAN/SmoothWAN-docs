## Setup after installing Speedify or setting up a WAN  
Navigate to Services->Pi-hole, set a WebUI password, click 'Trigger Install/Update' and then 'View log' tab:  
    
<img src="https://github.com/TalalMash/smoothwan-feeds/raw/main/luci-app-piholeconf/root/www/luci-static/resources/view/piholeconf/1.png" width="800"/>  
  
Installation takes approximately ~5-10 minutes, check the log tab.
You may need to trigger installation again on a lossy network, it's recommended to run Speedify prior to installation. 
Bottom of the log output after a successful installation should show installation status of the individual installed components:  
  
<img src="https://user-images.githubusercontent.com/96490382/156562378-88ac9b9b-afe0-4cc2-b1a2-549e8051f3d9.png" width="500"/>  

You can now visit Pi-hole admin page by the following address: http://172.17.17.3/admin  

***

### After installation  
* SmoothWAN DHCP settings are automatically configured after installation.  
* Updating Pi-hole is done by simply clicking "Trigger Install/Update", no further actions are needed.  
* Ad-blocking is automatically enabled, you can skip configuring Pi-hole or visiting the admin page.