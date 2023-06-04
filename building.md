# Building!
before we start building, we go to the main rom directory, if you aren't there already.

````
cd ~/crdroid
````

then we do 

````
. build/envsetup.sh
````


You have to do that for every time, you close your terminal or restart your device.

Then we can continue in a few ways.

To make sure your rom will build normally, we should do this first:

````
lunch
````

This will list all possible devices you can build for (many of these won't work, lol)

Select the number for your device and then this should be a result you want to get:
(you can also do ````lunch rom_devicecodename-userdebug.mk````)

````
============================================
PLATFORM_VERSION_CODENAME=REL
PLATFORM_VERSION=13
EVO_VERSION=evolution_crownlte-ota-tq2a.230505.002-05230200
EVO_BUILD_TYPE=OFFICIAL
TARGET_PRODUCT=evolution_crownlte
TARGET_BUILD_VARIANT=userdebug
TARGET_BUILD_TYPE=release
TARGET_ARCH=arm64
TARGET_ARCH_VARIANT=armv8-a
TARGET_CPU_VARIANT=cortex-a53
TARGET_2ND_ARCH=arm
TARGET_2ND_ARCH_VARIANT=armv8-a
TARGET_2ND_CPU_VARIANT=cortex-a53
HOST_OS=linux
BUILD_ID=TQ2A.230505.002
OUT_DIR=/home/spectre/ROMS/evolution/out
PRODUCT_SOONG_NAMESPACES=vendor/samsung/exynos9810-common device/samsung/exynos9810-common hardware/google/interfaces hardware/google/pixel hardware/samsung hardware/samsung/aidl/power-libperfmgr vendor/samsung/crownlte hardware/nxp hardware/qcom-caf/common/fwk-detect
============================================
````

if you get a result like this, you can go and try building. 

````
make bacon
````
#### this command can differ for the rom, ask the specific community if you need help

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/errors.md)

#### [• Beginning](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/Readme.md)
#### [• What do we want to build?](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/what.md)
#### [• Preparing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/preparing.md)
#### [• Syncing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/syncing.md)
#### [• Editing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)
#### [> Building](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/building.md)
#### [• Errors](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/errors.md)
#### [• End](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/end.md)