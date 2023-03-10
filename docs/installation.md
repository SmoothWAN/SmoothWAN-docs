<h3>(Note: An upcoming guide with better visuals is WIP)</h3>
<b>Speedify users: Free accounts are not supported (last update: March 2023)</b>
<h2>Installation using a smartphone as an example for quick setup</h2>
<b>Note:</b> Slate AX or Flint is recommended for ease of use due to built in stable Wi-Fi adapters, no extra hardware is needed.<br>
  
- Download and follow the instructions from the [release](https://github.com/TalalMash/SmoothWAN/releases) page. <br>
- Connect your hardware in a similiar way to this example: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1a.svg" width="400"/>
<h2><b>OR</b></h2>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1slate.svg" width="400"/><br>
- The Pi or Slate is now broadcasting as a Wi-Fi access point for easy configuration, connect to "SmoothWAN Setup", password: "brassworld": <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1.png" width="300"/> <br>
- Visit: http://172.17.17.2 there is no password set: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/2.png" width="300"/> <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/3.png" width="300"/> <br>
- You will be greeted with brief instructions in the UI, setup Speedify: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/4.png" width="300"/> <br>
- Click "Trigger Install/Update": <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/5.png" width="300"/> <br>
- Click "View Log" tab, it will show "Speedify is installed" at the end of the log after few seconds: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/6.png" width="300"/> <br>
- Head to Status->Overview: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/7.png" width="300"/> <br>
- Speedify app is now installed, login: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/8.png" width="300"/> <br>
- Setup a password for SmoothWAN admin page in System->Administration <br>
- All done, enjoy a reliable internet. <br>

***

- <b>Extra</b>: to change the USB ports / WAN name, head to Interfaces->Multi-WAN USB: <br> 
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/11.png" width="300"/> <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/12.png" width="300"/> <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/13.png" width="300"/> <br>
- <b>Pi specifics:</b>
  - Connect and configure a Wi-Fi AP/router if needed, the internal Wi-Fi of the Pi is unstable for general use, connect using RPi4's Ethernet port to a configured AP/router [(more info)](https://github.com/TalalMash/SmoothWAN/discussions/18#discussioncomment-2521688): <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/2a.svg" width="300"/> <br>
  - After connecting your mobile over the Wi-Fi AP/router, head over to Network->Wireless and disable Pi's Wi-Fi: <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/9.png" width="300"/> <br>
<img src="https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/10.png" width="800"/> <br>
