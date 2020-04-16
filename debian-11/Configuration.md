# Introduction

Installation and configuration of the different sofware must result to :

*Every actions (or quasi) can be easily with keyboard shortcuts (compiz)
*Remove unnecessary waste of space to keep focus, only a bar potentially autohideable is accepteable, (remove title, window decoration ...) (compiz)
*The position and size of the different applications must be remembered (compiz)
*Having a global menu (like MacOsX) and accessible with keyboard shortcut, (mate-panel with mutiny + xdotool)
*Having HUD to search in menu of the application with keyboard shortcut (mate-hud)
*Easy to put windows left, right, maximize, minimize with keyboard shortcuts (compiz grid)
*Having a searcheable launcher with a keyboard shortcut (rofi --show run)
*Having a searcheable task manager with a keyboard shortcut (rofi --show window)
*Keep short as possible as the shortcuts as the one in Windows

# Installation
Download debian-mate version (here 10) and then update to testing (11) if you want to have update up-to-date softwares.


# Post installation

## Update to testing in the /etc/apt/source.list
    sudo apt install gedit
    
Update /etc/apt/sources.list by adding contrib non-free repos, update to testing and comment security repository

    sudo gedit /etc/apt/sources.list
    
    # See https://wiki.debian.org/SourcesList for more information.
    deb http://deb.debian.org/debian testing main contrib non-free
    deb-src http://deb.debian.org/debian testing main contrib non-free

    deb http://deb.debian.org/debian testing-updates main contrib non-free
    deb-src http://deb.debian.org/debian testing-updates main contrib non-free

    #deb http://security.debian.org/debian-security/ buster/updates main
    #deb-src http://security.debian.org/debian-security/ buster/updates main


## Installation of firmware of ati drivers for radeon
Drivers are the kernel but need to have firmware from non-free repository).






# Software Installation

## From apt / snap
    sudo apt update

### Network

    sudo apt install curl chromium-browser torbrowser-launcher transmission
    
### Mutimedia  


    sudo apt install ubuntu-restricted-extras mpv handbrake sound-juicer brasero
    # sudo apt install libdvdnav4 libdvdread4 gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly libdvd-pkg
    sudo apt install digikam 
    
### Utilities   
    sudo apt install gedit
    
    sudo apt install git fdupes pdftk    
    sudo snap install intellij-idea-community --classic --edge

### Documents
    sudo apt install libreoffice
    sudo apt install calibre
    sudo apt install pdftk
    
### Other


