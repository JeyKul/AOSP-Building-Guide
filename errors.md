# Errors

On any error, you should try and read the error carefully. If you do that, you can figure out what is wrong and fix it. Read the error carefully and you may be able to fix the error! Else ask someone in your devices community for help.

Usually the build should continue now. 

## Common Errors

### Lineage Tree Errors

If you're working with a lineage tree, you might encounter errors related to livedisplay, touch, and hidl. To resolve these, edit the `common.mk` file located in `device/manufacturer/something-common`. Remove the lines referring to touch, hidl, and livedisplay, then restart the build.

### Error 137
This usually means that your machine ran out of ram. The `-j` option in the `make` command specifies the number of jobs (commands) that `make` can run simultaneously. Restart the build with for example

````make bacon -j[NumberOfJobs] ```` <- without brackets!!!


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