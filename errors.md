# Errors

On any error, you should try and read the error carefully. If you do that, you can figure out what is wrong and fix it. Read the error carefully and you may be able to fix the error! Else ask someone in your devices community for help.

Usually the build should continue now. 

### If its a lineage tree, you may get some errors about livedisplay, touch and hidl. 

Edit the common.mk file inside device/manifacturer/something-common and remove the lines talking about touch, hidl and livedisplay and restart the build.

### Error 137
This usually means that your machine ran out of ram. Restart the build with for example

````make bacon -j[AmountOfRamInGB] ```` <- without brackets!!!


Then your build should go as planned.


# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/end.md)

#### [• Beginning](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/Readme.md)
#### [• What do we want to build?](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/what.md)
#### [• Preparing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/preparing.md)
#### [• Syncing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/syncing.md)
#### [• Editing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)
#### [• Building](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/building.md)
#### [> Errors](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/errors.md)
#### [• End](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/end.md)