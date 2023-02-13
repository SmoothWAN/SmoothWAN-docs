<h1>Setting up OLED display for stats</h1> 
<h1>(Version 0.99.6->8 only!)</h1>

## Reference Diagram

<img src="https://user-images.githubusercontent.com/96490382/159758215-0ab75c25-10ed-4628-b1fa-7341327f053f.png" height=400>  
  
* Setup is plug and play, no configuration is needed.  
* Note that Speedify pauses stats on no network activity to save data.
Display output is enabled after Speedify is running.
## Recommended hardware  
![oled1](https://user-images.githubusercontent.com/96490382/159758422-d94381b5-4d25-40ea-a96c-b74e941d89db.PNG)  

- Pluggable I2C 128x64 pixel OLED module    

![image](https://user-images.githubusercontent.com/96490382/159759242-21c7cd0a-b613-4b92-b494-14c02174ff82.png)    

- Plug to the first left side of the pins as the picture above  

![image](https://user-images.githubusercontent.com/96490382/159758512-f56e7bcc-47de-44a9-9e95-ad58ebd5887a.png)    

- A transparent case with enough clearance works well

## Notes
* Stats are displayed only when Speedify is installed and running.<br>
* Preview after installation and power up:<br>
<img src="https://user-images.githubusercontent.com/96490382/159760745-5ab94ec4-1ae8-4f66-bc5c-938e9d871dc6.gif" height=400><br>
## Advanced
* You can customize the display and modify battery parameters at /etc/ssd/config.json<br>
* Refer to https://github.com/talalmash/SSD1306_OLED_json/<br>
* For modular PC/x86, and other boards, use the second I2C port and use wires (non-pluggable), you can change the i2c port and address in config.json if only one port is available.

!!! note "Custom battery scripts"
 
Pi UPS INA219:  
![image](https://user-images.githubusercontent.com/96490382/165628877-c3d9d892-5ed4-47e6-b535-68ffdf3c56e2.png)   
/etc/rc.local (append before exit 0)   

```
modprobe ina2xx
echo 'ina219 0x42' > /sys/bus/i2c/devices/i2c-1/new_device
```

/etc/ssd/bat.sh

```
#!/bin/sh

if [[ $(cat /sys/bus/i2c/devices/1-0042/hwmon/hwmon1/curr1_input | cut -b 1) != "-" ]]; then
        echo "CHG"
else
        VC=$(cat /sys/bus/i2c/devices/1-0042/hwmon/hwmon1/in1_input)
        if [[ $VC -le 8000 ]]; then
                echo "scale=2; ($VC - 6000) / 2400 * 100" | bc | sed 's!\.0*$!!' | tr -d '\n'
        echo -n "%"
        else
                echo -n "100"
        fi
fi
```
