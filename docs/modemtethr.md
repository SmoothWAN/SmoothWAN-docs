## USB Modems

Modems using RNDIS or "virtual Ethernet adapter" are easier to set up.  

### Suggested Models:

- Huawei's Wingle series
- All Huawei model variants updated after 2015 use RNDIS by default.

**Note:** MBIM, QMI, and other protocols aren't automatically configured. Be sure to disable the USB interface namer in the Speedify setup page before manually configuring a modem interface.

---

## USB WiFi Adapters in Client Mode

### Supported Models/Chipsets:

- [Check out "morrownr" community report compilation guide](https://github.com/morrownr/USB-WiFi)

As a better alternative, wireless repeaters with an Ethernet socket work as clients in bridge mode, and you can optionally hide the repeater SSID. This solution provides better stability, Wi-Fi 6E support, higher speeds, and improved range.

---

## Setup

1. Plug the dongle into a USB port that will remain fixed. Changing ports requires reconfiguration.
2. Restart or reboot SmoothWAN.
3. Configure in **Network → Wireless**.
4. Hit `Scan`, follow through, tick **Replace existing configuration**, and set the firewall to **RED zone**.
5. Done!
