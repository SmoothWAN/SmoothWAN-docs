<b>Speedify users: Free accounts are not supported (last update: March 2023)</b>
<h2>Installation using a smartphone as an example for quick setup</h2>
<b>Note:</b> Slate AX or Flint is recommended for ease of use due to built in stable Wi-Fi adapters, no extra hardware is needed.<br>
  
- Download and follow the instructions from the [release](https://github.com/TalalMash/SmoothWAN/releases) page. <br>
- Connect your hardware in a similiar way to this example: <br>
![](https://github.com/TalalMash/SmoothWAN-web/raw/main/Basic%20Setup%20Guide%20assets/1slate.svg)
![](assets/flintports.png)
- The Slate or Flint is now broadcasting as a Wi-Fi access point for easy configuration, connect your phone to Wi-Fi `SmoothWAN Setup 2.4 or 5Ghz` with password: `brassworld`: <br>
- In your browser, visit: http://172.17.17.2 there is no password set: <br>
![](assets/setup/1.webp)
![](assets/setup/2.webp)
- You will be greeted with brief instructions in the UI, if you need to connect to a Wi-Fi network to bond and use (WWAN), you can do up to 2 with 5G and 2.4G, skip the following steps if all your internet sources to be used (WAN) by Speedify are wired, head to `Simple Wi-Fi Setup`: 
![](assets/setup/3.webp)
![](assets/setup/4.webp)
**You can also change your access point SSID/Password here!**
![](assets/setup/5.webp)
**Enable the wireless WANs that you have configured**
![](assets/setup/6.webp)
![](assets/setup/7.webp)
**With all your WANs now configured, install Speedify:**
![](assets/setup/9.webp)
![](assets/setup/10.webp)
![](assets/setup/11.webp)
**All done!**
You can change your password in the administration page.
![](assets/setup/12.webp)

***
**Note**

Few devices are problematic with SmoothWAN built-in interface renamer (the unique name shown in the example as `USB_1f16`), you can disable this option in Speedify configuration page menu -> Options. The adapter naming will be named by the order of first detection e.g `usb0`, `usb1` etc which can be random on every power up. 
For data cap limit users, Speedify won't be able to tell which WAN to limit persistently in this mode.
![](assets/setup/13.webp)