# Nexus5

## Root

### Easy way
Root with (easier)
CF-Auto  + script
or with
Android SDK then launch ./android and install platform-tools

### Root with commands and some useful commands

See if the phone is connected

 adb devices
 
 List of devices attached 
 xxxxx	recovery
 
If you have 

 List of devices attached 
 ????????????	no permissions
 
Do

 sudo ./adb kill-server
 sudo ./adb start-server
 

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

### Tested : 

Stock (not many features, autonony is bad)

Slim Bean (dark mode, autonomy not bad).

### Best tested : Slim Bean 4.4.beta2

Kernel
======

### Tested : 
Franco (good autonomy)

Bricked (very good performance, good autonomy)

Chaos (good performance, good autonomy)

ElemantalX (good performance, good autonomy)

Faux (not working)

### Best : Bricked Kernel (best performance 20000 on Quadrant (with custom dalvik), 32000 on Antutu) and not bad on autonomy

Optimization
============

### Use custom dalviK
Use custom dalvik (http://forum.xda-developers.com/showthread.php?t=2546120)

Links
=====

http://androidforums.com/nexus-5-all-things-root/776309-nexus-5-all-things-root-guide.html

http://www.gizmodo.fr/2013/11/09/comment-rooter-google-nexus-5.html

http://androidforums.com/nexus-5-all-things-root/790362-nexus-5-rooting-guide.html

http://developer.android.com/sdk/index.html

http://www.forum-generationmobiles.net/t70828-tuto-aides-et-conseils-pour-savoir-comment-utiliser-le-twrp-recovery-explorations-et-explications-14112013

