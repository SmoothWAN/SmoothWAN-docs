#### Written by https://github.com/DalSoft  
### If you are using Speedify for privacy do a DNS leak test  

Depending on the configuration of devices (e.g. ISP's locked down modem / router) you plug into the WAN ports to bond - your ISP DNS servers may leak.   

  If this is something you don't want then:  
  1. Do an extended [dnsleaktest](https://www.dnsleaktest.com).  
  2. If your ISP's DNS server is shown, then uncheck the "Use DNS servers advertised by peer setting" on each of the WAN interfaces, and change the DNS server to 1.1.1.1 or whatever DNS server you prefer / trust.  
  <img src="https://user-images.githubusercontent.com/406007/199865411-3fab4de0-3c91-444b-9f13-eadb5440bb07.png" width="800" />
