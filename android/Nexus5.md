Nexus5
------

Root
====

Root with (easier)
CF-Auto  + script
or with
Android SDK then launch ./android and install platform-tools

See if the phone is connected

 adb devices

Reboot in bootloader mode

adb reboot bootloader

See if the phone is connected during the boot (you must be root under linux)

sudo ./fastboot devices

Unlock the bootloader

sudo ./fastboot oem unlock

Flash in recovery mode

fastboot flash recovery twrp-file-name.img


Rom
===

Tested : Stock, Slim Bean

Best tested : Slim Bean 4.4 

Kernel
======

Tested : Franco, Bricked, Faux

Best tested : Bricked Kernel (best performance 11000 on Quadrant, 32000 on Antutu) and not bad on autonomy


Links
=====

http://androidforums.com/nexus-5-all-things-root/776309-nexus-5-all-things-root-guide.html

http://www.gizmodo.fr/2013/11/09/comment-rooter-google-nexus-5.html

http://androidforums.com/nexus-5-all-things-root/790362-nexus-5-rooting-guide.html

http://developer.android.com/sdk/index.html

