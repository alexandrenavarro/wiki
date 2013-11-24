Nexus5
------

Root
====

http://androidforums.com/nexus-5-all-things-root/776309-nexus-5-all-things-root-guide.html

http://www.gizmodo.fr/2013/11/09/comment-rooter-google-nexus-5.html

http://androidforums.com/nexus-5-all-things-root/790362-nexus-5-rooting-guide.html

http://developer.android.com/sdk/index.html

http://www.phonandroid.com/forum/sony-et-android-pour-les-n


Root with (easier)
CF-Auto  + script
or with
Android SDK then launch ./android and install platform-tools

# See if the phone is connected
adb devices

# Reboot in bootloader mode
adb reboot bootloader

#  voir si le téléphone est bien connecté dans le boot (il faut être root sous linux)
sudo ./fastboot devices
# Débloquer le bootloader
sudo ./fastboot oem unlock

# Flash in recovery mode
fastboot flash recovery twrp-file-name.img


Rom
===

Tested : Stock, Slim Bean

Best tested : Slim Bean 4.4 

Kernel
======

Tested : Franco, Bricked, Faux

Best tested : Bricked Kernel (best performance 11000 on Quadrant, 32000 on Antutu) and not bad on autonomy

