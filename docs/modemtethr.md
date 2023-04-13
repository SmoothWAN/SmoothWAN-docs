## USB Modems

Modems using RNDIS or "virtual Ethernet adapter" are supported. 
Popular device:

- Huawei's Wingle series
- All Huawei model variants updated year 2015+ (TODO: add more info) use RNDIS by default.


MBIM, QMI, and others aren't automatically configured yet, be sure to disable USB interface namer in Speedify setup page before manually configuring a modem interface.


***

## USB WiFi Adapters in Client Mode
## Supported models/chipset:
- [AR9271](https://deviwiki.com/wiki/Atheros_AR9271#Table_of_Systems), tested models:
    - ALFA AWUS036NHA (beware of counterfeits)

Realtek, new Qualcomm Atheros (not to be confused with old Atheros), and Ralink are not reliable on Linux without custom drivers.  
Only Atheros `ath9k`,`ath9k_htc`,`ath10k` based AHB/PCI-e/USB are supported.  
Relevant details on this topic:
https://wireless.wiki.kernel.org/en/users/wi-fi-alliance-certification  

**TL;DR: USB Wi-Fi Adapters on Linux are a mess.**

As a better alternative, wireless repeaters with an Ethernet socket work as clients in bridge mode, and you can optionally hide the repeater SSID. This solution is a decent alternative for stability, Wi-Fi 6E support, higher speeds and better range.

## Setup
- Plug in the dongle to a USB port that will remain fixed, changing ports requires reconfiguration
- Restart/Reboot SmoothWAN
- Configure in Network -> Wireless 
- Hit `Scan` and follow through, tick `Replace existing configuration` and set firewall to RED zone
- Done!