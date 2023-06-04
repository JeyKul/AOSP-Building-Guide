# Editing!

Let's continue with editing the device trees. 

[We also made a script for that, check it out!](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/rename.md)

In that script you have to rename a few things...

````PRE```` means what the device tree was before. On 9810 devices its ````aosp_star2lte.mk````

````POST```` means what its going to be renamed to. For Lineage for example you do ````lineage_star2lte.mk````

````ROOTDIR```` is the foldername of your rom. You should execute the script in the HOME directory. 

````DEVICE```` means the device you are building for. ````star2lte```` is ````DEVICE2````. If you dont need to rename for multiple devices, you have to put a # before the other renames. Like that -> ````#mv $ROOTDIR/device/$MANIFACTURER/$DEVICE2````

````MANIFACTURER```` means the devices brand, like here its ````samsung````



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

you dont need to edit these for crdroid. Just check if the paths inside the files are existing. you open a file with `nano`

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

Many Roms, that allow you to go Official, have a extra git organization, to save/locate the devicetree for official devices. 
In there you can see, if `lineage_codename.mk` is something different. On spark its `spark_codename.mk`, On Arrow its `arrow_codename.mk', I think you get what I want to tell you! 

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

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/building.md)