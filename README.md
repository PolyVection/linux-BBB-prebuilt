# linux-BBB-prebuild
Prebuilt Beaglebone Black kernel with support for PlainDAC+ and PlainDSP.
See https://github.com/PolyVection/linux-BBB.git for source code.

Always perform a backup of your system and your data before using this files!


#Connect the hardware
Connect PlainDAC+BBB or PlainDSP-BBB as follows

1. P9.02 -> I2C address select (GND)
2. P9.27 -> LRCK
3. P9.41 -> DATA
4. P9.42 -> BCK
5. P9.25 -> MCLK
6. the power input pins (GND, 3v3, 5V) to the matching pins on your BBB.


# Install the custom kernel
1.  ssh to your BBB
2.  git clone https://github.com/PolyVection/linux-BBB-prebuild.git
3.  cd linux-BBB-prebuild
4.  sudo cp -r lib/* /lib
5.  sudo mkdir /boot/backup
6.  sudo mv /boot/initrd.img-* /boot/backup/
7.  sudo mv /boot/vmlinuz-* /boot/backup/
8.  sudo cp -r /boot/dtbs /boot/backup/
9.  sudo cp -r boot/* /boot
10. sync
11. sudo reboot
...
12. ssh to your BBB again
13. sudo su 
14. echo BB-PLAINDAC > /sys/devices/bone_capemgr*/slots
15. aplay -l -> now shows PlainDAC as card:1
16. speaker-test -D plughw:1 -c 2 -> to hear a test noise on L + R channel

