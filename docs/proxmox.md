## Installation using Proxmox
### Using Proxmox in VMware as a demo
Application: Running SmoothWAN alongside Ubuntu/Windows or containers.

- Download the VMDK image from the [release](https://github.com/TalalMash/SmoothWAN/releases) page.
- Download Proxmox ISO and flash to a USB drive using balenaEtcher:

![](assets/proxmox/1.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Boot up your PC/server with the USB drive plugged in (you may have use the boot menu to select the drive)
- Follow the screenshots and set the IP address within the subnet of SmoothWAN (172.17.17.0/24)

![](assets/proxmox/2.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/3.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/4.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/5.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/6.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/7.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/8.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Create a new VM:

![](assets/proxmox/9.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/10.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/11.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/12.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/13.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/14.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/15.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/16.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/17.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Upload, extract and insert the image using the command line (works with Windows, MacOS, Linux):

![](assets/proxmox/18.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/19.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/20.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}


- Double-click the unused image to add the drive:

![](assets/proxmox/21.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/22.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}


- Change the boot order in *Options* and enable the drive:

![](assets/proxmox/23.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}


- Start the VM and click console to view SmoothWAN starting up (will reboot twice):

![](assets/proxmox/25.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Visit SmoothWAN WebUI (172.17.17.2) to check if it is running:

![](assets/proxmox/26.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Time to add the rest of the ethernet ports to SmoothWAN VM as WANs, assuming you have 3 extra ports in this example:

![](assets/proxmox/27.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/28.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/31.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/32.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/33.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Click *Apply Configuration* then head to the VM settings page and configure the new adapters after stopping the VM:

![](assets/proxmox/38.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/35.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/37.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Do the same for the rest of the ports
![](assets/proxmox/39.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Start and check SmoothWAN setup page for the newly added WANs, a colourful network icon indicates that the interface is up (other than looking at the IP):

![](assets/proxmox/40.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}

- Hint: to use 2 or more LAN ports (e.g. 2 WANs, 2 LANs in this example), remove the desired interface from the bridge ( `vmbr1` not removed in screenshots for clarity), and append interface to the first bridge, SmoothWAN uses the first (`vmbr0`) as LAN:

![](assets/proxmox/41.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
![](assets/proxmox/42.webp){: style="max-height:700px;border:6px solid #d2ccf1;"}
