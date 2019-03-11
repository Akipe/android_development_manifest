# Personal Android manifest

This is my personal manifest for Android device ROM developement. Currently I develop for Motorola Moto G5 (cedric).

Android ROM for cedric :
- LineageOS 15.1 (arm64)
- TWRP 7.1 (arm64)

# How to prepare build
You will need to download the manifest, download the Android source, and then execute the compilation.

## Prepare the manifest
```
# Download the manifest
git clone https://github.com/Akipe/android_development_manifest
```

## Cedric LineageOS 15.1 (arm64)
Prepare and download files :
```
# Initialize project 
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-7.1 --current-branch
# Create the directory where manifest are store
mkdir .repo/local_manifests
# Create link for lineageos manifest to the project directory
ln -s /path/to/manifest/directory/cedric_lineageos-15.1-64.xml .repo/local_manifest
# Download all sources
repo sync -j4 -c --force-broken 
```
Building :
```
source build/envsetup.sh
lunch
select cedric
make -j$(nproc) recoveryimage
```

## Cedric TWRP 7.1 (arm64)
Prepare and download files :
```
# Initialize project 
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-7.1 --current-branch
# Create the directory where manifest are store
mkdir .repo/local_manifests
# Create link for lineageos manifest to the project directory
ln -s /path/to/manifest/directory/cedric_lineageos-15.1-64.xml .repo/local_manifest
# Download all sources
repo sync -j4 -c --force-broken 
```
Building :
```
source build/envsetup.sh
lunch
select cedric
```
