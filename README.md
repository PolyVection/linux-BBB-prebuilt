# linux-BBB-prebuild
Prebuilt Beaglebone Black kernel with support for PlainDAC+ and PlainDSP.
See https://github.com/PolyVection/linux-BBB.git for source code.

Always perform a backup of your system and your data before using this files!

With the new kernel + modules + dts in place load the virtual PlainDAC cape with:

echo BB-PLAINDAC > /sys/devices/bone_capemgr*/slots

