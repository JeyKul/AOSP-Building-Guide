````
#!/bin/bash

read -p "Enter PRE: " PRE
read -p "Enter POST: " POST
read -p "Enter ROOTDIR: " ROOTDIR

DEVICE1=starlte
DEVICE2=star2lte
DEVICE3=crownlte
MANUFACTURER=samsung

echo "Renaming $PRE.dependencies to $POST.dependencies..."
echo "You can make $POST.dependencies whatever your ROM needs."

mv $ROOTDIR/device/$MANUFACTURER/$DEVICE1/$PRE.dependencies $ROOTDIR/device/$MANUFACTURER/$DEVICE1/$POST.dependencies
mv $ROOTDIR/device/$MANUFACTURER/$DEVICE2/$PRE.dependencies $ROOTDIR/device/$MANUFACTURER/$DEVICE2/$POST.dependencies
mv $ROOTDIR/device/$MANUFACTURER/$DEVICE3/$PRE.dependencies $ROOTDIR/device/$MANUFACTURER/$DEVICE3/$POST.dependencies

echo "Renaming ${PRE}_device.mk to ${POST}_device.mk..."
mv $ROOTDIR/device/$MANUFACTURER/$DEVICE1/${PRE}_$DEVICE1.mk $ROOTDIR/device/$MANUFACTURER/$DEVICE1/${POST}_$DEVICE1.mk
mv $ROOTDIR/device/$MANUFACTURER/$DEVICE2/${PRE}_$DEVICE2.mk $ROOTDIR/device/$MANUFACTURER/$DEVICE2/${POST}_$DEVICE2.mk
mv $ROOTDIR/device/$MANUFACTURER/$DEVICE3/${PRE}_$DEVICE3.mk $ROOTDIR/device/$MANUFACTURER/$DEVICE3/${POST}_$DEVICE3.mk

echo "${PRE} -> ${POST} in files"
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE1/${POST}_$DEVICE1.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE1/AndroidProducts.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE2/${POST}_$DEVICE2.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE2/AndroidProducts.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE3/${POST}_$DEVICE3.mk
sed -i "s/${PRE}/${POST}/" $ROOTDIR/device/$MANUFACTURER/$DEVICE3/AndroidProducts.mk
````
