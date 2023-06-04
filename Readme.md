# How to build AOSP

We have to prepare a lot, before starting with syncing things and then actually building.
---
Depending how many devices you want to build with, you can even build on some weaker pc.

If you ask me for an minimal requirement, id say

| Cores        | Ram           | Storage  |
| ------------- |:-------------:| -----:|
| 4 Cores, 4 Threads      | 16GB RAM | Full 256GB |

If you use 256GB storage you HAVE TO delete .repo folder to have enough storage for building. 
get more storage to not have to do that!
***
Recommended would be any specs better than these or atleast 512GB or more storage.
With that kind of specs, a build would roughly take 1 Hour and 30 Minutes.

You meet the minimal requirements?
Great!

Now you need to search what Linux distro you want. If you want to use this Linux install only for building AOSP, I recommend you going for Ubuntu. If you have enough storage, you can even use an VM (i'd do that, if you are a little over the minimal requirements!), instead of actually installing it on your PC, since we only use CPU power. (make sure to have CPU acceleration in any kind enabled, so you get the full performance out of your VM!)

# [Next ->](https://github.com/JeyKul/AOSP-Building-Guide/blob/main/what.md)
