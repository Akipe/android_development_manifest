# TWRP tree for Cedric and Motorola MSM8937 Family

## Twrp
```
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-7.1
repo sync
source build/envsetup.sh
lunch
select cedric
make -j$(nproc) recoveryimage
```