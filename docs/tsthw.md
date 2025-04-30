**Note:** USB flash drives are not recommended for this purpose. Use an SD card with a USB reader if there is no internal storage. [More details here](https://github.com/SmoothWAN/SmoothWAN/discussions/109).

---

## USB Ethernet Adapters

**Not recommended:**

- TP-Link and U-Green ASIX-based chipset
- Non-brand name Realtek-based chipset
- Flat cable type and/or cable length >15cm
- Using USB 2.0 hubs

---

## Mobile Hotspots (Plug and Play)

- Verizon 8800L
- AT&T Nighthawk M6 Pro

---

## Network Switchs for MACVLAN

- Unmanaged NETGEAR GS108UK
- Unmanaged ~8 USD TOTOLINK S808G

---

## USB Tethering

- Android USB tethering may be limited to ~150 Mbit due to USB networking emulation.
- iOS 13+ USB tethering is not officially supported due to practicality issues:
    - You need to tap "Trust" on every reconnection/hiccup with `usbmuxd`, unlike iTunes.
    - If the cellular signal is weak, tethering will automatically disconnect, requiring USB physical reconnection to continue tethering.
    - [Partial workarounds](https://openwrt.org/docs/guide-user/network/wan/smartphone.usb.tethering#extras).
