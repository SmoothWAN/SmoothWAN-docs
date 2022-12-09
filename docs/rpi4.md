### Ports layout
<img src="https://raw.githubusercontent.com/TalalMash/SmoothWAN/88f9bfccce30fef116f0d509d05e2df78f8f8b2d/devconfigs/rpi4/files/www/luci-static/bootstrap/mwanusb.svg"/>
### Troubleshooting

## Restarting on large downloads or livestream test
Indicates poor power supply, use the official RPi power supply or a 5.3V adapter and a USB-PD Type-C cable.*

## Red LED flashing erratically
Indicates poor power supply.*
* You can reduce power consumption as well as performance (~180Mbit) by editing `config.txt` in SD and adding `arm_freq=1000` at the end of the file.

## Unable to connect to "SmoothWAN Setup" SSID
Setup in close proximity to the Pi, signal is not an indicator to use.  
Cause: RPi's internal Wi-Fi "ACK-drop" interval is very short and not adjustable.