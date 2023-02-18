_**Quick build hints**_  
??? note "Raspberry Pi 4 and PC"

    - Grab your imagebuilder device target archive from: https://downloads.openwrt.org/releases/22.03.3/targets/ 
    - Clone repo and copy the corresponding device from devconfigs and packages to imagebuilder root. 
    - Run "sh build.sh" 
    - Compiled image is in `bin/...` 
  

??? note "Gl.iNet Slate AX / Flint"

    - `git clone https://github.com/gl-inet/gl-infra-builder.git` 
    - `sudo apt install build-essential clang flex g++ gawk gcc-multilib gettext \
    git libncurses5-dev libssl-dev python3-distutils rsync unzip zlib1g-dev \
    file wget` 
    - `python3 setup.py -c configs/config-wlan-ap.yml` 
    - `cd wlan-ap/openwrt` 
    - Copy the content of the `flint` or `slateax` folder in main SmoothWAN repo to current directory
    - `./scripts/gen_config.py target_wlan_ap-gl-ax1800 luci` (replace ax1800 with axt1800 for Slate AX)
    - `git clone https://github.com/TalalMash/smoothwan-feeds.git`
    - `./scripts/feeds update -a`
    - `./scripts/feeds install -a`
    - `./sideload-glibc.sh'
    - `make -j20` 
    - Compiled image is in `bin/targets/ipq...` 

**Notes:**  
  
- For compiling SmoothWAN packages, compile `smoothwan-feeds` with OpenWRT build system.
- Pre-compiled packages are included for easy customization, quick builds and imagebuilder-only setup.<br>  
- GL.iNet builds are full-builds and require comprehensive setup. More at: https://github.com/gl-inet/gl-infra-builder   
* `glibc` is included from Debian Buster since Speedify does not provide `musl` builds. Lib included: `libc6_2.31-13+deb11u2`, and `libgcc1_8.3.0-6_armhf` for armv7. 
Binaries are sideloaded during build. Check `sideload-glibc.sh` for sources.
- All binaries are generated on Github Actions
    - Engarde : <https://github.com/SmoothWAN/engarde>
    - TinyFEC : <https://github.com/SmoothWAN/tinyfecVPN>
    - ntopng : <https://github.com/SmoothWAN/SmoothWAN-chroot-imagebuilder>

