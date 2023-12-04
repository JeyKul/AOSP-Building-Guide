# Preparing

```
mkdir ~/crdroid && cd ~/crdroid
```
##### crdroid is an virable for the creation of a folder. you can name it whatever you want. Just make sure that all other commands are mathing your virable.

Great! now we are inside the crDroid folder, ready to install dependencies!

Some dependencies may or may not exist in your chosen distro. In my experience, this isnt that big of a deal, cause these dependencies are usually in your system some other way!

UBUNTU:

````
sudo apt install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git git-lfs gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5 libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-gtk3-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
````
DEBIAN:
````
sudo apt install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git git-lfs gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5 libncurses5-dev libsdl1.2-dev libssl-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
````


If you dont have an Debian based Linux installed, you will have to search the dependencies yourself! 

````Android Dependencies [LinuxDistrobution]```` <- without brackets.

If these Dependencies are done installing, we are going to sync the ROM. Usually every ROM has their own repo, to show how to do that correctly. Just check their git-page and find it!

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/syncing.md)

#### [• Beginning](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/Readme.md)
#### [• What do we want to build?](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/what.md)
#### [> Preparing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/preparing.md)
#### [• Syncing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/syncing.md)
#### [• Editing](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/editing.md)
#### [• Building](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/building.md)
#### [• Errors](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/errors.md)
#### [• End](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/end.md)
