````
#!/bin/bash

PRE=aosp
POST=lineage
ROOTDIR=crdroid
DEVICE1=starlte
DEVICE2=star2lte
DEVICE3=crownlte
MANIFACTURER=samsung


echo renaming $PRE.dependencies to $POST.dependencies
echo you can make $POST.dependencies to whatever 
echo your rom needs

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE1/$PRE.dependencies $ROOTDIR/device/$MANIFACTURER/$DEVICE1/$POST.dependencies

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE2/$PRE.dependencies $ROOTDIR/device/$MANIFACTURER/$DEVICE2/$POST.dependencies

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE3/$PRE.dependencies $ROOTDIR/device/$MANIFACTURER/$DEVICE3/$POST.dependencies


echo renaming ${PRE}_device.mk to ${POST}_device.mk...

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE1/${PRE}_$DEVICE1.mk $ROOTDIR/device/$MANIFACTURER/$DEVICE1/${POST}_$DEVICE1.mk

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE2/${PRE}_$DEVICE2.mk $ROOTDIR/device/$MANIFACTURER/$DEVICE2/${POST}_$DEVICE2.mk

mv $ROOTDIR/device/$MANIFACTURER/$DEVICE3/${PRE}_$DEVICE3.mk $ROOTDIR/device/$MANIFACTURER/$DEVICE3/${POST}_$DEVICE3.mk


echo ${PRE} -> ${POST} in files

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE1/${POST}_$DEVICE1.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE1/AndroidProducts.mk

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE2/${POST}_$DEVICE2.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE2/AndroidProducts.mk

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE3/${POST}_$DEVICE3.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANIFACTURER/$DEVICE3/AndroidProducts.mk
````