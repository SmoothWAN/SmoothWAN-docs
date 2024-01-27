## USB Modems

Modems using RNDIS or "virtual Ethernet adapter" are easier to setup. 

Suggested models:

- Huawei's Wingle series
- All Huawei model variants updated year 2015+ use RNDIS by default.


MBIM, QMI, and others aren't automatically configured yet, be sure to disable USB interface namer in Speedify setup page before manually configuring a modem interface.


***

## USB WiFi Adapters in Client Mode
## Supported models/chipset:
- [Check out "morrownr" community report compilation guide](https://github.com/morrownr/USB-WiFi)

As a better alternative, wireless repeaters with an Ethernet socket work as clients in bridge mode, and you can optionally hide the repeater SSID. This solution is a decent alternative for stability, Wi-Fi 6E support, higher speeds and better range.

## Setup
- Plug in the dongle to a USB port that will remain fixed, changing ports requires reconfiguration
- Restart/Reboot SmoothWAN
- Configure in Network -> Wireless 
- Hit `Scan` and follow through, tick `Replace existing configuration` and set firewall to RED zone
- Done!