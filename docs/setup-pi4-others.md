## Installation using a smartphone as an example for quick setup

### Download and Follow the Instructions
- Download and follow the instructions from the [release](https://github.com/TalalMash/SmoothWAN/releases) page.  

    * Use [EtchDroid](https://etchdroid.app/) on Android, Mac if you are on iOS.

### Connect Your Wired Internet Connections

![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1a.svg){: style="max-height:700px;border:6px solid #d2ccf1;"}

### Connect Your Phone to Wi-Fi
- The Pi is now broadcasting as a Wi-Fi access point, disable mobile data and connect your phone to Wi-Fi `SmoothWAN Setup` with password: `brassworld`.  
- For PC or x86 router (Protectli, Qotom etc) users, use the first wired LAN port and a laptop instead of smartphone.  
- In your browser, visit: http://172.17.17.2, there is no password set:  

![](assets/setup/1.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/setup/2.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

### Install Speedify

![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/4.png){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/setup/9.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

### Login to Speedify
- Head back to the home page **Status -> Overview**  

![](assets/setup/10.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/setup/11.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

### Change Web Login Password
You can change your web login password in the administration page  

![](assets/setup/12.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

***
### Optional steps

??? tip "Change WAN Names"
    To change the USB ports / WAN name, head to Interfaces->Multi-WAN USB:

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/11.png){: style="max-height:700px;border:6px solid #d2ccf1;"}

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/12.png){: style="max-height:700px;border:6px solid #d2ccf1;"}

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/13.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}

??? tip "Using a Wi-Fi router or a Wi-Fi access point"
    The internal Wi-Fi of the Pi is unstable for general use, connect using RPi4's Ethernet port to a configured AP/router:

    1. Login to the Wi-Fi router's admin page or phone app.
    2. Set "LAN IP address" to `172.17.17.5` (you can change the last number by preference from 5-10)
    3. Disable "DHCP Server"
    4. Now plug SmoothWAN appliance to the LAN port instead of WAN.  

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/2a.svg){: style="max-height:700px;border:6px solid #d2ccf1;"}

    You have just created a "Bridged Access Point".  
    You can access the Wi-Fi router setup page from `172.17.17.5`

    Few examples with common vendors:
    - TP-Link  
    ![image](https://user-images.githubusercontent.com/96490382/162148977-397dfdae-56b8-43ae-8314-72eb1a3088cd.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}
    - Asus  
    ![image](https://user-images.githubusercontent.com/96490382/162149499-ec290f69-8cf0-4de5-827f-66d772110eac.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}
    ![image](https://user-images.githubusercontent.com/96490382/162149580-8745d63f-3bb2-4b5d-9aca-755a06f2dd61.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}
    - Linksys  
    ![image](https://user-images.githubusercontent.com/96490382/162150449-d08b8244-c984-4b80-8809-9157e2533abb.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}
    - Netgear  
    ![image](https://user-images.githubusercontent.com/96490382/162150782-8f989520-31e6-42b7-908d-72990da3ebe5.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}
    - Tenda  
    ![image](https://user-images.githubusercontent.com/96490382/162151069-23342150-3f05-4dc0-8efe-ff7b666298c6.png){:    style="max-height:700px;border:6px solid #d2ccf1;"}

    After connecting your mobile over the Wi-Fi AP/router, head over to Network->Wireless and disable Pi's Wi-Fi:

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/9.png){: style="max-height:700px;border:6px solid #d2ccf1;"}

    ![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/10.png){: style="max-height:700px;border:6px solid #d2ccf1;"}

***
