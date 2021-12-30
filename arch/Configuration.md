# Introduction

Installation and configuration of the different sofware must result to :

* Every actions (or quasi) can be easily with keyboard shortcuts (bspwm + sxhkd)
* Remove unnecessary waste of space to keep focus (remove title, window decoration, global menu or transparent top bar ...) and have a a global menu (like MacOsX) or transparent topbar on the right or no topbar if not really need (bspwm with or without polybar)
* The position and size of the different applications must be predictable or remember (bspwm)
* Easy to put windows on left, right, maximize, minimize with keyboard shortcuts (bspwm)
* Having a searcheable launcher with a keyboard shortcut (rofi)
* Having a searcheable task manager with a keyboard shortcut (rofi)
* Keep shortcuts as possible as the shortcuts as the one in Windows (default + sxhkd)
* Have a dark theme (adwaita-dark with lxappearance / qt5ct)


# Installation (through arc iso + archifi install script, harder)
Download last arch iso.

## Basic Configuration to install arch
Set your keyboard layout
    
    loadkeys fr
    loadkeys fr-bepo
    # rlaisp^ eo=kpjl (write the line above on qwerty)
    
If you don't have ethernet, you can configure your wifi connection in commandline through https://www.mankier.com/1/iwctl    
    
    iwctl
    
Retrieve your device ogenerally wlan0
    
    station list

Retrieve your network

    station wlan0 get-networks

Connect to your network
    
    station wlan0 connect yournetwork

    
## Installation with Archfi

Download and run archfi installer

    curl -LO matmoul.github.io/archfi
    sh archfi
    
If you have an EFI pc, set your /boot on your efi partition


# Installation (through Calam-Arch-Installer, easier)

Download Calam-Arch-Installer iso.

On partition config, don't forget to create /boot/efi partition (needed on efi generally the case on machine post 2016).

Select only the package needed (on a desktop AMD cpu):
    base-devel
    pacman-contrib
    xorg-server
    xorg-init
    xf86-input-libinput
    networkmanager
    grub
    efibootmgr
    dosfstools
    amd-ucode
    efitools
    
Select only the package for video (with amd/ati gpu)
    xf86-video-amdgpu

Select at least one desktop environmet + d (I let mate but it will be remove once bspwm + sxhkd will be installed)
    mate
    lightdm
    lightdm-gtk-greeter
    lightdm-gtk-greeter-settings

# Post Installation
TODO
