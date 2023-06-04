````
#!/bin/bash

PRE=aosp
POST=lineage
ROOTDIR=crdroid

echo renaming $PRE.dependencies to $POST.dependencies
echo you can make $POST.dependencies to whatever 
echo your rom needs

mv $ROOTDIR/device/samsung/starlte/$PRE.dependencies $ROOTDIR/device/samsung/starlte/$POST.dependencies

mv $ROOTDIR/device/samsung/star2lte/$PRE.dependencies $ROOTDIR/device/samsung/star2lte/$POST.dependencies

mv $ROOTDIR/device/samsung/crownlte/$PRE.dependencies $ROOTDIR/device/samsung/crownlte/$POST.dependencies


echo renaming ${PRE}_device.mk to ${POST}_device.mk...

mv $ROOTDIR/device/samsung/starlte/${PRE}_starlte.mk $ROOTDIR/device/samsung/starlte/${POST}_starlte.mk

mv $ROOTDIR/device/samsung/star2lte/${PRE}_star2lte.mk $ROOTDIR/device/samsung/star2lte/${POST}_star2lte.mk

mv $ROOTDIR/device/samsung/crownlte/${PRE}_crownlte.mk $ROOTDIR/device/samsung/crownlte/${POST}_crownlte.mk


echo ${PRE} -> ${POST} in files

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/starlte/${POST}_starlte.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/starlte/AndroidProducts.mk

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/star2lte/${POST}_star2lte.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/star2lte/AndroidProducts.mk

sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/crownlte/${POST}_crownlte.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/samsung/crownlte/AndroidProducts.mk
````