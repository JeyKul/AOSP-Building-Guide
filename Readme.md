# How to build AOSP

We have to prepare a lot, before starting with syncing things and then actually building.
---
Depending how many devices you want to build with, you can even build on some weaker pc.

If you ask me for an minimal requirement, id say

| Cores        | Ram           | Storage  |
| ------------- |:-------------:| -----:|
| 4 Cores, 4 Threads      | 16GB RAM | Full 256GB |

Recommended would be any specs better than these or atleast 512GB or more storage.
With that kind of specs, a build would roughly take 1 Hour and 30 Minutes.

You meet the minimal requirements?
Great!

Now you need to search what Linux distro you want. If you want to use this Linux install only for building AOSP, I recommend you going for Ubuntu. If you have enough storage, you can even use an VM (i'd do that, if you are a little over the minimal requirements!), instead of actually installing it on your PC, since we only use CPU power. (make sure to have CPU acceleration in any kind enabled, so you get the full performance out of your VM!)


# What do we want to build?

There are many AOSP projects, you can decide building. 

A few more popular are

1. [LineageOS](https://lineageos.org/)
2. [ArrowOS]()
3. [crDroid]()
4. [PixelExperience (+)]()

 If you have decided on what to build, we are going to sync the project. 
 ##### I will show examples for the ROM crDroid.

First we will create our working enviroment

# Preparing

```
mkdir crdroid && cd crdroid
```
##### crdroid is an virable for the creation of a folder. you can name it whatever you want. Just make sure that all other commands are mathing your virable.

Great! now we are inside the crdroid folder, ready to install dependencies!

Some dependencies may or may not exist in your chosen distro. In my experience, this isnt that big of a deal, cause these dependencies are usually in your system some other way!

````
sudo apt install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git git-lfs gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5 libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-gtk3-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
````

If these Dependencies are done installing, we are going to sync the ROM. Usually every ROM has their own repo, to show how to do that correctly. Just check their git-page and find it!

# Syncing

````
repo init -u https://github.com/crdroidandroid/android.git -b 13.0 --git-lfs
`````

##### This is for syncing crDroid. Your rom may be different and it probaly has another name for that repo as well.

after that is done, we are going to check if your device has an Manifest, which can be useful to make the syncing easier!

You should just ask the Maintainer for your device, if they have an Manifest. If they dont have one, you can just skip to ```repo sync```

If your device got a Manifest, we are going to import that!

````
git clone https://github.com/samsungexynos9810/local_manifests-V2 -b thirteen-slsi-next .repo/local_manifests
````

Done? Then lets get to our final command for the next hour or two!

To sync the stuff to your local drive, we are going to do 

````
repo sync
````
This will sync all stuff you need (on an good rom)

# Repo sync is done!

Great, the first long waiting time is now done.

If your device doesnt have a manifest, read here now. Else continue to "Editing!"

Damn, your device didnt have a manifest, we have to import the trees ourselves. 
### Usually not that hard!

First we search a repo, suidable for your device. I wont go to depth on that. But this part of the tutorial is going for a73!

If you have found its repo, we are going to clone following repos: 

+ device_samsung_a73xq
+ device_samsung_sm7325-common
+ vendor_samsung_a73xq
+ vendor_samsung_sm7325-common
+ kernel_samsung_sm7325

If you are good in noticing patterns, you might have noticed, that the names are

+ Paths
+ Manifacturer
+ device codename
+ 

so, you then usually go and do 

````
git clone https://github.com/samsung-778/android_device_samsung_a73xq device/samsung/a73xq
````

so the underscore almost always turn into a /

you do a git clone for every of these 5 (or more for multiple devices) repos, with their right path. The android_ is to be ignored... Its a glorification to make it more sorted or something.

# Editing!

Let's continue with editing the device trees. 

On crDroid you often dont need to make many changes, since many trees base of lineageos.

to check what your device is based on, you do 

````
ls device/vendor/codename
````

If there is are files named 

````
lineage_codename.mk
lineage.dependencies
````

you dont need to edit much for crdroid. Just check if the paths inside the files are existing. you open a file with `nano`

````
nano lineage_codename.mk
nano lineage.dependencies
nano BoardConfig.mk
nano Android.mk
nano AndroidProducts.mk
nano device.mk
`````
If everything is correct in these files, you can go to Building!

But what if you don't want to build crDroid, but something like SparkOS?

Many Roms, that allow you to go Official have a extra git organization, to save/locate the devicetree for official devices. 
In there you can see, if `lineage_codename.mk` is something different. On spark its `spark_codename.mk`, On Arrow its `arrow_codename.mk', i think you get what i want to tell you! 

If you have to rename files, you do 
````
mv old_filename.mk new_filename.mk
`````
you may also have to edit inside these files, just check all paths inside the files.

In these roms, we have 
````
$(call inherit-product, vendor/arrow/config/common.mk)
```` 
inside `arrow_codename.mk` which usually changes for many roms. same logic with checking official devices and pathes on that!

Done? lets go to Building!



# Building!
before we start building, we go to the main rom directory, if you aren't there already.

````
cd ~/crdroid
````

then we do 

````
. build/envsetup.sh
````


you have to do that for every time, you close your terminal or restart your device.

then we can continue in a few ways.

To make sure your rom will build normally, we should do this first:

````
lunch
````

This will list all possible devices you can build for (many of these won't work, lol)

select the number for your device and then this should be a result you want to get:

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

if you get a result like this, you can go building. 

````
make bacon
````
#### this command can differ for the rom, ask the specific community if you need help

# Errors

On any error, you should try and read the error carefully. If you do that, you can figure out what is wrong and fix it. Read the error carefully and you may be able to fix the error! Else ask someone in your devices community for help.

usually the build should continue now. 

### If its a lineage tree, you may get some errors about livedisplay, touch and hidl. 

Edit the common.mk file inside device/manifacturer/something-common and remove the lines talking about touch, hidl and livedisplay and restart the build.

### Error 137
This usually means that your machine ran out of ram. Restart the build with for example

````
make bacon -j[AmountOfRamInGB]
````

Then your build should go as planned.


# End
If you have any questions regarding building Android you can try asking [me for help](t.me/jeykul) on telegram.

thanks for reading!
