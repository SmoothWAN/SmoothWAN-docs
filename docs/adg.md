##AdGuard Home is a local network-wide advertising blocker

*How to enable adblocking*

- Visit https://172.17.17.2:3000 or your LAN IP :3000 and click "Enable protection"  
<img style="border:6px solid #d2ccf1;" src="/assets/adg.webp" style="max-height:300px"/>

*Notes*

- You can change password in the configuration tab.


###Due to popular request and leak-proof DNS, ADGH is the default DHCP server
To use OpenWrt's DNSmasq, edit `/etc/config/dnsmasq` and add to the bottom of the file:
```
config dnsmasq
        option domainneeded '1'
        option localise_queries '1'
        option rebind_protection '1'
        option rebind_localhost '1'
        option local '/lan/'
        option domain 'lan'
        option expandhosts '1'
        option authoritative '1'
        option readethers '1'
        option leasefile '/tmp/dhcp.leases'
        option resolvfile '/tmp/resolv.conf.d/resolv.conf.auto'
        option localservice '1'
        option ednspacket_max '1232'
        list server '8.8.8.8'
```