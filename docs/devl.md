_**Quick build:**_
- Grab your imagebuilder device target archive from: https://downloads.openwrt.org/releases/21.02.1/targets/
- Clone repo and copy the corresponding device from devconfigs and packages to imagebuilder root.
- For OLED dashboard, build "ssd" from https://github.com/TalalMash/SSD1306_OLED_json or use the bundled executable/
- Run "sh build.sh"
- Images will be located in bin/
- Note:   
 1- For compiling SmoothWAN packages, compile smoothwan-feeds with OpenWRT build system. Pre-compiled packages are included for easy customization, quick builds and imagebuilder-only setup.<br>
 2- GL.iNet builds are full-builds and require comprehensive setup. More at: https://github.com/gl-inet/gl-infra-builder  


***


* `glibc` is included from Debian Buster since Speedify does not provide `musl` builds. Lib included: `libc6_2.31-13+deb11u2`, `libgcc1_8.3.0-6_armhf` for armv7. Concerning security with the bundled binaries, you can compare the checksum of the included binaries by extracting the Debian package.
* Bundled "ssd" binary (SSD1306 OLED support) is built from https://github.com/TalalMash/SSD1306_OLED_json with Dockerfile (x86:buster,arm64-qemu:focal), e.g:  
`docker build -t ssd .`  
`docker run -d -t ssd`
`docker cp <containerid>:/root/SSD1306_OLED_json/ssd .`  
Commit `f55d893` Docker build checksums:    
x86: `3535b79f3a95a9f2edf9b1be1c3e14bf624f72d05159fe14912a0091cb8500cd`  
arm64: `22adbde150f1de78dc73223654b6988839d6ca8168530c4b082e054a104690c4`  
Will be packaged and compiled with OpenWRT in v1.0
* Model-View Lua based LuCI apps are bugged with newer OpenWRT versions, the following apps are included in `files` and not packaged for compatibility:  
` luci-app-wifibasic  `  
` luci-app-swanportfw `   
` luci-app-swaninterfaces  `  