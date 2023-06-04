# Syncing

````
repo init -u https://github.com/crdroidandroid/android.git -b 13.0 --git-lfs
`````

##### This is for syncing crDroid. Your rom may be different and it probaly has another name for that repo as well.

After that is done, we are going to check if your device has an Manifest, which can be useful to make the syncing easier!

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
This will sync all stuff you need. (on an good rom)

# Repo sync is done!

Great, the first long waiting time is now done.

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)

## If your device doesn't have a manifest, read here now.

Damn, your device doesn't have a manifest, we have to import the trees ourselves. 
### Usually not that hard!

First we search a repo, suitable for your device. I wont go to depth on that. But this part of the tutorial is going for Samsung Galaxy A73!

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



So, you then usually go and do:

````
git clone https://github.com/samsung-778/android_device_samsung_a73xq device/samsung/a73xq
git clone https://github.com/samsung-778/device_samsung_sm7325-common device/samsung/sm7325-common
...
...
````

NOTE: The underscore always turn into a /

You do a git clone for every of these 5 (or more for multiple devices) repos, with their right path. The android_ is to be ignored... Its a glorification to make it more sorted or something.

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)

#### [• Beginning](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/Readme.md)
#### [• What do we want to build?](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/what.md)
#### [• Preparing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/preparing.md)
#### [> Syncing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/syncing.md)
#### [• Editing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)
#### [• Building](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/building.md)
#### [• Errors](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/errors.md)
#### [• End](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/end.md)