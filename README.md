This is the Android device configuration for Xperia Z

To setup a tree and build images for the device do the following:

* repo init as described by Google over at: http://source.android.com/source/downloading.html
* Copy 'yuga.xml' to .repo/local_manifests/yuga.xml
* repo sync
* lunch full_c6603-userdebug
* cd device/sony/c6603/_yuga_patches && ./patchall.sh && cd -
* cd kernel/sony/* && ./_build.sh && cd -
* make

To flash the images produced make sure your device is unlocked, as described on
http://unlockbootloader.sonymobile.com/

Enter fastboot mode on the device by pressing volume up while inserting the USB
cable or execute adb reboot bootloader.

* fastboot flash userdata out/target/product/c6603/userdata.img
* fastboot flashall

Reflashing userdata is not necessary every time, but incompatibilities with
previous content might result in a device that doesn't boot. If this happens
try to reflash just the userdata again.
