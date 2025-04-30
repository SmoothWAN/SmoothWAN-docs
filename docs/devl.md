# Quick Build Hints

## Raspberry Pi 4 and PC

**Steps:**

- Download the ImageBuilder archive for your device target from:  
- Clone the repository and copy the corresponding device folder from `devconfigs` and `packages` into the ImageBuilder root directory.
- Run the build script:  
  ```sh
  sh build.sh
  ```
- The compiled image will be located in the `bin/...` directory.

---

## GL.iNet Flint and Slate AX 
**(No longer supported – repository is down)**

**Steps:**

- For v1.0 and above, follow the Raspberry Pi/PC instructions instead.
- Clone the GL.iNet builder:
  ```sh
  git clone https://github.com/gl-inet/gl-infra-builder.git
  ```
- Install dependencies:
  ```sh
  sudo apt install build-essential clang flex g++ gawk gcc-multilib gettext \
  git libncurses5-dev libssl-dev python3-distutils rsync unzip zlib1g-dev \
  file wget
  ```
- Run setup:
  ```sh
  python3 setup.py -c configs/config-wlan-ap.yml
  cd wlan-ap/openwrt
  ```
- Generate build config (replace `ax1800` with `axt1800` for Slate AX):
  ```sh
  ./scripts/gen_config.py target_wlan_ap-gl-ax1800 luci
  ```
- Clone SmoothWAN feeds:
  ```sh
  git clone https://github.com/SmoothWAN/smoothwan-feeds.git
  ```
- Copy the contents of the `flint` or `slateax` folder from the main SmoothWAN repo to the current directory.
- Update and install feeds:
  ```sh
  ./scripts/feeds update -a
  ./scripts/feeds install -a
  ```
- Run the glibc sideloader:
  ```sh
  ./sideload-glibc.sh
  ```
- Copy the `.config` file from the `flint` or `slateax` folder to the current directory.
- Build the firmware:
  ```sh
  make -j20 V=sc
  ```
- The compiled image will be located in `bin/targets/ipq...`.

---

## Notes

- To compile SmoothWAN packages, build `smoothwan-feeds` using the OpenWrt build system.
- Pre-compiled packages are included for easy customization, quick builds, and ImageBuilder-only setups.
- GL.iNet builds require a full build process and comprehensive setup. More details at:  
  https://github.com/gl-inet/gl-infra-builder
- `glibc` is included from Debian Buster to support running Speedify on `musl`-based OpenWrt.  
  Included libraries:
    * `libc6_2.31-13+deb11u2`
    * `libgcc1_8.3.0-6_armhf` (for armv7)
  These binaries are sideloaded during the build. See `sideload-glibc.sh` for sources.
- All binaries are generated using GitHub Actions:
    * Engarde: https://github.com/SmoothWAN/engarde
    * TinyFEC: https://github.com/SmoothWAN/tinyfecVPN
    * ntopng: https://github.com/SmoothWAN/SmoothWAN-chroot-imagebuilder
