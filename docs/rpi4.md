
## Port Layout

<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN/88f9bfccce30fef116f0d509d05e2df78f8f8b2d/devconfigs/rpi4/files/www/luci-static/bootstrap/mwanusb.svg"/>

---

## Troubleshooting

### Restarting on Large Downloads or Livestream Test

This indicates a poor power supply. Use the official RPi power supply or a 5.3V adapter with a USB-PD Type-C cable.

---

### Red LED Flashing Erratically

This also indicates a poor power supply.

---

### Unable to Connect to "SmoothWAN Setup" SSID

Set up in close proximity to the Pi. Signal strength is not a reliable indicator to use.  
!!! note "Note"
    The RPi's internal Wi-Fi "ACK-drop" interval is very short and not adjustable, dropping far clients as a result. 

    Use it for managing the device only.
---

For maximum stability, you can reduce power consumption (and performance) to ~180-Mbit by editing `config.txt` on the SD card and adding `arm_freq=1000` at the end of the file.
