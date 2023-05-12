_**Quick build hints**_  
??? note "Raspberry Pi 4 and PC"

    - Get your imagebuilder device target archive from: https://downloads.openwrt.org/releases/22.03.3/targets/ 
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
    - `./scripts/gen_config.py target_wlan_ap-gl-ax1800 luci` (replace ax1800 with axt1800 for Slate AX)
    - `git clone https://github.com/SmoothWAN/smoothwan-feeds.git`
    - Copy the content of the `flint` or `slateax` folder in main SmoothWAN repo to current directory
    - `./scripts/feeds update -a`
    - `./scripts/feeds install -a`
    - `./sideload-glibc.sh`
    - Copy the `.config` file from the `flint` or `slateax` folder in main SmoothWAN repo to current directory
    - `make -j20 V=sc` 
    - Compiled image is in `bin/targets/ipq...` 

    
??? note "NanoPi R6S"
    - Replace ~/build with a directory of your choice (builds outside docker)
    - `docker run --name ubuntu18 --privileged -it -v ~/build:/work ubuntu:18.04 bash`
    - Note! to resume after exit do:
    - `docker start ubuntu18`
    - `docker exec -it ubuntu18 bash`
    - Continue:
    - `apt update && apt install git python build-essential clang flex bison g++ gawk gcc-multilib g++-multilib gettext git libncurses5-dev libssl-dev python3-distutils rsync unzip zlib1g-dev file wget`
    - `cd /work && mkdir friendlywrt21-rk3588`
    - `git clone https://github.com/friendlyarm/repo --depth 1 tools`
    - `git config --global user.email "anon@anon.com"`
    - `git config --global user.name "anon"`
    - `tools/repo init -u https://github.com/friendlyarm/friendlywrt_manifests -b master-v21.02 -m rk3588.xml --repo-url=https://github.com/friendlyarm/repo  --no-clone-bundle`
    - Press Enter
    - `tools/repo sync -c  --no-clone-bundle`
    - `cd friendlywrt && git clone https://github.com/SmoothWAN/SmoothWAN.git && mkdir smoothwan-feeds`
    - `cd SmoothWAN && git checkout npi-r6s && cp -rP devconfigs/npir6s/. .. && cp -rP packages/. ../smoothwan-feeds && cd ..`
    - `sh sideload-glibc.sh`
    - `./scripts/feeds update -a`
    - `./scripts/feeds install -a`
    - `FORCE_UNSAFE_CONFIGURE=1 make -j16` (reduce -j16 to -j8 for <10GB RAM)
    - Run on fresh start only:
    - `./build.sh uboot && ./build.sh kernel`
    - Create the image, use emmc-img for flashable EMMC.
    - `cd .. && ./build.sh sd-img` 
    - Compiled image is in `out` folder, you can use your file browser to access the folder assigned in the first step.

**Notes:**  
  
- For compiling SmoothWAN packages, compile `smoothwan-feeds` with OpenWRT build system.
- Pre-compiled packages are included for easy customization, quick builds and imagebuilder-only setup.<br>  
- GL.iNet builds are full-builds and require comprehensive setup. More at: https://github.com/gl-inet/gl-infra-builder   
* `glibc` is included from Debian Buster for running Speedify on `musl` built OpenWrt. Lib included: `libc6_2.31-13+deb11u2`, and `libgcc1_8.3.0-6_armhf` for armv7. 
Binaries are sideloaded during build. Check `sideload-glibc.sh` for sources.
- All binaries are generated on Github Actions
    - Engarde : <https://github.com/SmoothWAN/engarde>
    - TinyFEC : <https://github.com/SmoothWAN/tinyfecVPN>
    - ntopng : <https://github.com/SmoothWAN/SmoothWAN-chroot-imagebuilder>
- SmoothWAN images GH Actions builds TBD

