# android_device_wiko_rainbow_lite_4g
Device tree from TWRP Builder

#Command to compil this device tree
mkdir WorkerDir && cd WorkerDir
wget -q https://github.com/TwrpBuilder/twrp-sources/releases/download/omni_twrp-5.1.1-cleaned/omni_twrp-5.1.1_cleaned.tar.xz -O twrp.tar.xz
tar -xJf twrp.tar.xz --directory ./ && rm twrp.tar.xz
git clone https://github.com/clecle226/android_device_wiko_rainbow_lite_4g.git device/wiko/rainbow_lite_4g
git clone https://github.com/TwrpBuilder/android_device_generic_twrpbuilder.git device/generic/twrpbuilder
git clone https://github.com/omnirom/android_bootable_recovery.git bootable/recovery --depth=1
source build/envsetup.sh && lunch omni_rainbow_lite_4g-eng && make -j16 recoveryimage

#Method to give stock recovery.img
in shell adb -> Pass setprop persist.tinno.debug 1
(https://twitter.com/fs0c131y/status/938741187158183942)
and go adb shell in root (su)
make a dd command from recovery to sdcard
use TWRPBuilder
Compil

#Run custom recovery
You CAN'T flash recovery on device because recovery partition is too small
BUT you can boot on this rom.
-> Boot in fastboot mode
and enter "fastboot oem unlock-tinno" to unlock fucking locking
Enjoy with "fastboot boot recovery.img"
