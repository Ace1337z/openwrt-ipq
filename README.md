 



## Quickstart

1. Clone this repository:
   ```bash
   git clone https://github.com/Ace1337z/openwrt-ipq -b 24.10-nss
   ```
2. Update feeds:
   ```bash
   ./scripts/feeds update
   ./scripts/feeds install -a
   ```
3. Copy over the seed file
   ```bash
   cp nss-setup/config-nss.seed .config
   ```
4. Open the `.config` in a text editor, find your device, and remove the "#" and change `"is not set"` to `"=y"`

   Example:
   ```diff
   -# CONFIG_TARGET_qualcommax_ipq807x_DEVICE_dynalink_dl-wrx36 is not set
   +CONFIG_TARGET_qualcommax_ipq807x_DEVICE_dynalink_dl-wrx36=y
   ```
6. Generate the full config
   ```bash
   make defconfig V=s
   ```
7. enter menuconfig to edit
   ```bash
   make menuconfig
   ```
8. Now run full build
   ```bash
   make download -j$(nproc) V=s
   make -j$(nproc) V=s
   ```
 if want to clone package
 ```bash
git clone https://github.com/Ace1337z/luci-app-cpu-status.git package/feeds/luci/luci-app-cpu-status
git clone https://github.com/Ace1337z/luci-app-tinyfilemanager.git package/feeds/luci/luci-app-tinyfilemanager   
git clone https://github.com/Ace1337z/luci-theme-argon.git package/feeds/luci/luci-theme-argon
git clone https://github.com/Ace1337z/luci-app-argon-config.git package/feeds/luci/luci-app-argon-config
git clone https://github.com/solomonricky/luci-app-modeminfo.git package/feeds/luci/luci-app-modeminfo
```
