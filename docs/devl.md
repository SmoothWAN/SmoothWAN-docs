_**Quick build hints**_  
??? note "Raspberry Pi 4 and PC"

    - Grab your imagebuilder device target archive from: https://downloads.openwrt.org/releases/21.02.1/targets/ 
    - Clone repo and copy the corresponding device from devconfigs and packages to imagebuilder root. 
    - For OLED support, build "ssd" from https://github.com/TalalMash/SSD1306_OLED_json or use the bundled executable/ 
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
    - `make -j20` 
    - Compiled image is in `bin/targets/ipq...` 

**Notes:**  
  
- For compiling SmoothWAN packages, compile smoothwan-feeds with OpenWRT build system. Pre-compiled packages are included for easy customization, quick builds and imagebuilder-only setup.<br>  
- GL.iNet builds are full-builds and require comprehensive setup. More at: https://github.com/gl-inet/gl-infra-builder   
* `glibc` is included from Debian Buster since Speedify does not provide `musl` builds. Lib included: `libc6_2.31-13+deb11u2`, `libgcc1_8.3.0-6_armhf` for armv7. Concerning security with the bundled binaries, you can compare the checksum of the included binaries by extracting the Debian package.
* Bundled "ssd" binary (SSD1306 OLED support) is built from https://github.com/TalalMash/SSD1306_OLED_json with Dockerfile (x86:buster,arm64-qemu:focal), e.g:  
`docker build -t ssd .`  
`docker run -d -t ssd`
`docker cp <containerid>:/root/SSD1306_OLED_json/ssd .`  
Commit `f55d893` Docker build checksums:    
x86: `3535b79f3a95a9f2edf9b1be1c3e14bf624f72d05159fe14912a0091cb8500cd`  
arm64: `22adbde150f1de78dc73223654b6988839d6ca8168530c4b082e054a104690c4`  
Will be packaged and compiled with OpenWRT in v1.0
* Model-View Lua based LuCI apps are incosistent with newer OpenWRT ubus versions, the following apps are included in `files` and unpackaged for compatibility:  
` luci-app-wifibasic  `  
` luci-app-swanportfw `   
` luci-app-swaninterfaces  `  
