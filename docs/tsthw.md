### USB Hubs
* Waveshare USB 3.2 Gen1 And Gigabit Ethernet HUB HAT by @nickpoorman (longterm test unconfirmed)

### USB Ethernet Adapter
* Kensington K33981WW

**Not recommended:**
* TP-Link and U-Green ASIX-based chipset
* Non-brand name Realtek-based chipset 
* Flat cable type and/or cable length >15cm
* Using USB 2.0 hubs

### Mobile Hotspot
* Verizon 8800L by @chalk4#0933 (longterm test unconfirmed)
* AT&T Nighthawk M6 Pro by @chalk4#0933 (longterm test unconfirmed)

### Power Supply
* Samsung Type-C chargers (most models no-load = 5.2V)
* Official Raspberry Pi 4 USB-C Power Supply
* QwikFone QC3.0 Car charger

### Network Switch
* Managed TP-LINK TL-SG108E
* Unmanaged NETGEAR GS108UK
* Unmanaged TOTOLINK S808G (budget)
 
### SD card
* SanDisk Ultra SDSQUNS-032G-GN3MN 32GB
* SanDisk Industrial MLC MicroSD SDHC UHS-I Class 10
* SanDisk 32GB High Endurance Video (longterm test unconfirmed)

***

## Notes:
* Submit a PR or discussion post to add fully tested hardware (optionally: for 2 months or more) followed by your username.
* Tests are not recommendations, community reports are not always accurate, use the list for reference only.
* Android USB tethering may be limited to ~150 Mbit due to networking emulation.
* iOS 13+ USB tethering is not officially supported since it is impractical:
    - Need to tap "Trust" on every power up with `usbmuxd` unlike iTunes
    - If cellular signal is weak, tethering will automatically disconnect requiring physical reconnection to continue tethering.
    - [Partial workarounds](https://openwrt.org/docs/guide-user/network/wan/smartphone.usb.tethering#extras)
