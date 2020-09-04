# Introduction

Installation and configuration of the different sofware must result to :

* Every actions (or quasi) can be easily with keyboard shortcuts (openbox)
* Remove unnecessary waste of space to keep focus (remove title, window decoration, global menu or transparent top bar ...) and have a a global menu (like MacOsX) or transparent topbar on the right (openbox with polybar)
* The position and size of the different applications must be remembered (openbox)
* Easy to put windows on left, right, maximize, minimize with keyboard shortcuts (openbox)
* Having a searcheable launcher with a keyboard shortcut (rofi)
* Having a searcheable task manager with a keyboard shortcut (rofi)
* Keep shortcuts as possible as the shortcuts as the one in Windows (default + openbox)
* Have a dark theme (adwaita-dark with lxappearance)


# Installation
Download debian-standard with non-free  (here 10)  and then update to testing (11) if you want to have update up-to-date softwares


# Post Installation

## Post Installation if you come from debian-standard
    su
    sudo adduser anavarro sudo

You have to logout and login.

    sudo apt install firefox-esr lightdm openbox

If you can not set your custom keyboard layout use and restart

    sudo localectl set-keymap fr-bepo
    dpkg-reconfigure keyboard-configuration
    
You can set your custom layout through

    setxkbmap -model pc105 -layout fr -variant bepo 

or graphically through

    ibus-setup

## Installation of nonfree firmware if you come from a normal debian
Drivers are the kernel but need to have firmware from non-free repository if you not downloaded a debian-non-free
    sudo apt install firmware-linux-nonfree # for firmware-amd-graphics mainly

## Window Manager : OpenBox

### Installation
    sudo apt install openbox
    cd ~/.config/openbox
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/openbox/rc.xml
    cp rc.xml.1 rc.xml
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/openbox/autostart
    chmod a+x autostart

### Installation of software started with openbox session
    sudo apt install feh compton polybar
    
#### Theme
Retrieve Adwaita-Dark-openbox from https://www.google.com/search?client=firefox-b-e&q=Adwaita-Dark-openbox and set in ObConf
    
    obconf

On Theme tab, select Adwaita-Dark-openbox

    sudo apt install lxappearance fonts-ubuntu
    
    lxappearance

On Widget, set Adwaita-dark and DefaultFont Ubuntu 11
On Other, set Toolbar Style Icons only and Small toolbar icon

### Keyboard Layout
If after the start of openbox the layout is not correct (compared to the one in login manager), check throught bar / keyboard layout manager is correctly set with Bus Preference notably

## Update to testing in the /etc/apt/source.list
Update /etc/apt/sources.list by adding contrib non-free repos, update to testing and comment security repository

    sudo micro /etc/apt/sources.list
    
    # See https://wiki.debian.org/SourcesList for more information.
    deb http://deb.debian.org/debian testing main contrib non-free
    deb-src http://deb.debian.org/debian testing main contrib non-free

    deb http://deb.debian.org/debian testing-updates main contrib non-free
    deb-src http://deb.debian.org/debian testing-updates main contrib non-free

    #deb http://security.debian.org/debian-security/ testing/updates main
    #deb-src http://security.debian.org/debian-security/ testing/updates main

# Software Installation

## From apt 
    sudo apt update

### Accessories
#### File Editor
    sudo apt install micro
Adopted : micro (memory 30mo, have terminal mode, classical keyshortcuts)

#### Archive Manager
    sudo apt install file-roller
    
#### Window Compositor
    sudo apt install compton

#### Disk Usage
    sudo apt install gnome-disk-utility
    
#### Pdf Document Viewer
    sudo apt install zathura

Adopted : zathura (low memory, simple)

Tested but not select : atril (basic menu)

Tested but not selected : onkular (too many dependency to qt).

Tested but not selected : evince (same me but does not have real menu bar, hide some polybar info on the right)
    
    
#### Menu for launcher
    sudo apt install alacarte

### Education

#### Typing Learning
    sudo apt install klavaro

### Graphics  

#### Image Viewer
    sudo apt install sxiv
    sudo apt install feh
    sudo apt install eog
    
Adopted sxiv : faster to open, cool shortcuts (miss just to print the image)

Adopted just for wallpaper : feh

Adopted as second choice : eog just for printing quickly.

TODO see if only one instance app.

#### Image Manager (if you want to classify your pictures)
    sudo apt install digikam 
    
### Internet

#### Web Browser
    sudo apt install firefox-esr wget curl
    sudo apt install chromium 
    
#### Torrent Client
    sudo apt install transmission
    
### Office
    sudo apt install libreoffice

### Sound & Video
#### Video Player
    sudo apt install mpv

Adopted : mpv (only video, light)

Tested but not adopted : vlc (have menu)

#### Music Player
    sudo apt install moc

Adopted : moc (terminal music player)

Tested but not adopted : audacious (more memory)

Tested but not adopted : clementine (more memory)

Tested but not adopted : rhythmnbox (more memory)

#### DVD Ripper
    sudo apt install handbrake

#### DVD Burner
    sudo apt install brasero
    
#### Audio Controller 
    sudo apt install pulseaudio-utils volumeicon-alsa pavucontrol
    
#### News Group 
//TODO
    
### Utilities   
    sudo apt install policykit-1-gnome xdotool fdupes git jq unrar-free p7zip exfat-utils exfat-fuse rename
    
// TODO fix back when change input videos does not wake up screen?
// Seems to be a problem in lightdm and openbox, use gdm3 
// Launch gnome-screensaver &
// dbus-send --type=method_call --dest=org.gnome.ScreenSaver /org/gnome/ScreenSaver org.gnome.ScreenSaver.Lock

#### Book Manager (if you use kindle)
    sudo apt install calibre

### System Tools

#### File Explorer
    sudo apt install thunar

Adopted : lf (terminal)

Adopted (second choice) : thunar     

Tested but not selected : nautilus (navigation with keys less easy than thunar)

#### Terminal
    sudo apt install stterm bash-completion
    sudo apt install mate-terminal 

Adopted stterm : faster and low memory usage of any other terminal (12mo), need to be recompile to use with micro correctly, need to be used with tmux or use some patches.

Adopted second choice : mate-terminal

Tested but not selected gnome-mate-terminal : very close to mate-terminal without transparency (40 mo)


#### Launcher
    sudo apt install rofi

Adopted rofi : very fast and manage window selection.

#### Monitor
    sudo apt install htop

Adopted htop : fast, low memory usage and customizable

Tested but not selected gnome-monitor-systeme : use more memory, less information

Tested but not selected mate-monitor-system : use more memory, less information

#### Disks
    sudo apt install baobab gnome-disk-utility udiskie    

#### Scanner
    sudo apt install simple-scan

Adopted simple-scan : works, no concurrency.
    
#### Printer Server    
    sudo apt install task-print-server system-config-printer
   
### Preferences / Control Center
    sudo apt install lxappearance
//TODO qt5 themimg with gtk    

### Login 
    sudo apt install lightdm

### Lock
    sudo apt install light-locker
    
### Panel Bar
    sudo apt install polybar

Adopted polybar : moving window with openbox works, higly customisable, transparency.

Tested but not selected tint2 : size for moving window with openbox does not any work with %    
    
### Font 
    sudo apt install font-manager
    sudo apt install fonts-ubuntu fonts-material-design-icons-iconfont

### Bluetooth (if needed)
    sudo apt install bluetooth blueman 
    
# Custom Configuration / Installation for some applications
   
## Feh (Wallpaper)
    sudo apt install feh
    cd ~/.config/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/wallpaper.png

## Polybar
    sudo apt install fonts-ubuntu fonts-material-design-icons-iconfont
    sudo apt install polybar
    mkdir ~/.config/polybar
    cd ~/.config/polybar
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/polybar/config

See the resolution of bug for tray icon transparency https://github.com/polybar/polybar/issues/913

## Compton
    sudo apt install compton
    
Needed if you want to have transparency window notably for polybar.

## Lightdm
    sudo apt install lightdm
    sudo apt install light-locker
    
Show config
    lightdm --show-config

Use lightdm-gtk-greeter-settings to configure some options like themes, wallpaper, add keyboard layout.

Modify greeter-hide-users=false in /usr/share/lightdm/lightdm.conf.d/01_debian.conf and in /etc/lightdm/lightdm.conf
Add default-user=anavarro in /etc/lightdm/lightdm.conf

Modify background = /home/anavarro/Picture/wallpaper.png in /etc/lightdm/lightdm-gtk-greeter.conf
No . in a directory in the path accepted.

Add in your autostart to lock automatically after 300 s (5 min)
    
    xset s 300 &
    light-locker --lock-after-screensaver 1&

## Alacarte
    sudo apt install alacarte
    
Add Items 
Lock : dm-tool lock
Shutdown : systemctl poweroff
Restart : systemctl reboot
Logout : openbox --exit

It will add in ~/.local/share/applications/xxx.desktop files you can customize.

## Conky (optional)
If it works

    sudo apt install conky-all 
    
else
    
    cd Applications
    curl -sL -o conky-x86_64.AppImage $(curl -sL https://api.github.com/repos/brndnmtthws/conky/releases/latest | jq --raw-output '.assets[0] | .browser_download_url')
    chmod +x ./conky-x86_64.AppImage
    ./conky-x86_64.AppImage -C > ~/.conkyrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.conkyrc
    
## Lf

### Installation
Download the package and install in Applications
    
    sudo apt install mediainfo highlight

### Configuration
    
    cd .config/lf
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/lfrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/preview.sh
    chmod a+x preview.sh
    

# diskie (automount of usb drive)
    sudo apt install udiskie    
    
Just need to launch udiskie when you need. You can launch at startup or with --tray if want to have notification notably.

### Association files
Use a graphical File Manager like Thunar to associate your default application  or command below

#### Open a file with the default application
    xdg-open file.txt

#### See a filetype of a file 
    xdg-mime query filetype photo.jpeg

#### See the default application for a mime type
    xdg-mime query default image/jpeg

#### Default application for a mime type
    xdg-mime default feh.desktop image/jpeg

#### All default application for all mime type
    cat /usr/share/applications/mimeinfo.cache
    cat ~/.local/share/applications/mimeapps.list

#### All default applications
Text Editor : txt,sh,markdown -> micro

    xdg-mime default micro.desktop text/plain
    xdg-mime default micro.desktop text/markdown
    xdg-mime default micro.desktop text/x-maven+xml
    xdg-mime default micro.desktop text/x-yaml
    xdg-mime default micro.desktop text/x-java
    xdg-mime default micro.desktop text/x-chdr
    xdg-mime default micro.desktop text/x-csrc
    xdg-mime default micro.desktop text/x-readme
    xdg-mime default micro.desktop text/x-makefile
    xdg-mime default micro.desktop text/x-gradle
    xdg-mime default micro.desktop application/xml
    xdg-mime default micro.desktop application/x-shellscript
    

Image Viewer : jpg/png/gif -> default sxiv

    xdg-mime default sxiv.desktop image/jpeg
    xdg-mime default sxiv.desktop image/png
    xdg-mime default sxiv.desktop image/gif

Document Viewer : pdf -> org.pwmt.zathura-pdf-poppler.desktop

    xdg-mime default org.pwmt.zathura-pdf-poppler.desktop application/pdf
    
Compressed files : zip,tar.gz -> file-roller

    xdg-mime default org.gnome.FileRoller.desktop application/zip
    xdg-mime default org.gnome.FileRoller.desktop application/x-compressed-tar
  
Videos : avi,mkv,mp4

    xdg-mime default mpv.desktop video/x-msvideo 
    xdg-mime default mpv.desktop video/x-matroska
    
### Stterm

#### Installation
   sudo apt install stterm
   
#### Configuration / Compilation
Install Xlib header
    sudo apt install xxxxxxxx
    
Compile with make clean install from my fork (https://github.com/alexandrenavarro/st.git)

Fixes / Improvements : 
* Improvement : increase from 12 to 13
* Fix problem for micro for Shift + Home
* Fix problem for micro for Ctrl + Home
* Fix problem for micro for Shift + Ctrl + End 
* Fix problem for micro for Shift + End
* Fix problem for micro for Ctrl + End
Fixes do not work
* Fix problem for micro for Shift + Ctrl + Home : it does not work (it should, the mask is no recognize), let Ctrl + Home
* Fix problem for micro for Ctrl + Shift + Up : I don't know sequence code terminal, so prefer to let like Ctrl + Up
* Fix problem for micro for Ctrl + Shift + Down : I don't know sequence code terminal, so prefer to let like Ctrl + Down

Patch :
https://st.suckless.org/patches/alpha/

    patch -p0 < st-alpha-0.8.2.diff

Change alpha to 0.9

## Micro
    sudo apt install micro
    mkdir ~/.config/micro/
    cd ~/.config/micro
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/binding.json


Ctrl+Shift+Home (do nothing), Ctrl+Shift+Up (do the Ctrl+Up) and Ctrl+Shift+Down (do the Ctrl+Down) and does not work properly with stterm, see ssterm

See bug on bindings https://github.com/zyedidia/micro/issues/1628 and hybrid relative number feature https://github.com/zyedidia/micro/issues/1639


## TMux
    sudo apt install tmux
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.tmux.conf

## Firefox

### Installation
    sudo apt install firefox

### Configuration
* Install vimium plugin
* Install fox gesture plugin
* Reshow Menu bar (to see better polybar)

## Alacarte
    sudo apt install alacarte

## Java / Kotlin / Maven / Gradle
    curl -s "https://get.sdkman.io" | bash 
    source "$HOME/.sdkman/bin/sdkman-init.sh"
    sdk install java
    sdk install kotlin
    sdk install maven
    sdk install gradle
    sdk install kscript
    
### moc
    sudo apt install moc
    mkdir -p ~/.moc/themes/
    cd ~/.moc/themes/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/themes/kiss_theme
    cd ~/.moc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/config
    

### Etcher
Download AppImage of Etcher, add alacarte and run it.

## Intellij

### Configuration
Change some shorcuts
* Editor Actions | Move Caret to Code Block : CTRL + [ (equivalent)
* Editor Actions | Move Caret to Paragrah : CTRL + UP / Down (equivalent)
* Main menu | Navigate | Search Everywhere : CTRL + F3 (in addition of Shift / Shift)
* Main menu | Navigate | Back : Alt + Left (in addition of ALT + CTRL + Left)
* Main menu | Navigate | Forward : Alt + Right (in addition of ALT + CTRL + Right)
* Main menu | Tool Window | Project : Alt + Shift + "
* Main menu | Edit | Find | Replacet : Ctrl + H (in addition of Ctrl + R)


# Printer

## Installation
    sudo apt install task-print-server system-config-printer
    
Add rights to your user (voir https://wiki.debian.org/CUPSPrintQueues?action=show&redirect=PrintQueuesCUPS#webinterface)
    
    usermod -a -G lpadmin yourusername
    
And go to to configure your printer http://localhost:631/admin or use 
Install the one with driverless
    
    
## Epson EcoTank ET-4750
Search ET-4700 http://download.ebz.epson.net/dsc/search/01/search/searchModuleFromResult

### Printer (proprietary driver)
By default, it works but you can have more options (not really needed) are added

http://download.ebz.epson.net/dsc/search/01/search/searchModuleFromResult

Caution, not able to install propretary driver because lsb package does not exist on debian buster (it changed).

### Scanner
For Scanner, download Scanner Driver
Follow documentation (https://download3.ebz.epson.net/dsc/f/03/00/10/86/60/cbe4b348661d3be89ed8bb01b112ded41e756976/imagescanv3_man_e.pdf)

    tar xvzf imagescan-bundle-ubuntu-19.10-3.62.0.x64.deb.tar.gz
    ./install.sh 
    cd core
    sudo dpkg -i imagescan_3.62.0-1epson4ubuntu19.10_amd64.deb
    cd ../plugins
    sudo dpkg -i imagescan-plugin-networkscan_1.1.3-1epson4ubuntu19.10_amd64.deb
    
Edit Configuration files    
    micro /etc/imagescan/imagescan.conf

with

    [devices]
    net.udi = networkscan:esci://192.168.0.6:1865
    net.vendor = Epson 
    net.model = Epson EcoTank ET-4750
    net.name = Epson EcoTank ET-4750


# Distribution ugrade

Update your /etc/apt/source.list

    sudo apt update 
    sudo apt upgrade
    sudo apt dist-upgrade


# Configuration to do to have the same shortcuts as Windows

### Keyboard shortcuts in Windows
* See https://support.microsoft.com/kn-in/help/12445/windows-keyboard-shortcuts

#### Copy, paste, and other general keyboard shortcuts
* Ctrl + X 	                    Cut the selected item (DONE by default)
* Ctrl + C (or Ctrl + Insert)   Copy the selected item (DONE by default)
* Ctrl + V (or Shift + Insert) 	Paste the selected item (DONE by default)
* Ctrl + Z 	                    Undo an action (DONE by default)
* Alt + Tab 	                Switch between open apps (DONE by default)
* Alt + F4 	                    Close the active item, or exit the active app (Change with Super + Q)
* Windows logo key  + L 	    Lock your PC (DONE by default)
* Windows logo key  + D 	    Display and hide the desktop (DONE by configuration)
* F2                            Rename the selected item (DONE by default)
* F3                            Search for a file or folder in File Explorer (Ctrl + F In Nautilus)
* F4                            Display the address bar list in File Explorer (Ctrl + L In Nautilus)
* F5                            Refresh the active window (DONE by default)
* F6                            Cycle through screen elements in a window or on the desktop (DONE by default)
* F10                           Activate the Menu bar in the active app (DONE on some app)
* Alt + F8                      Show your password on the sign-in screen (No, Resize window)
* Alt + Esc                     Cycle through items in the order in which they were opened (No)
* Alt + underlined letter       Perform the command for that letter (No)
* Alt + Enter                   Display properties for the selected item (DONE by default)
* Alt + Spacebar                Open the shortcut menu for the active window (DONE by default, but removed if no decoration)
* Alt + Left arrow              Go back (DONE by default)
* Alt + Right arrow             Go forward (DONE by default)
* Alt + Page Up                 Move up one screen (DONE by default)
* Alt + Page Down               Move down one screen (DONE by default)
* Ctrl + F4                     Close the active document (in apps that are full-screen and let you have multiple documents open at the same time) (DONE by default)
* Ctrl + A                      Select all items in a document or window (DONE by default)
* Ctrl + D (or Delete)          Delete the selected item and move it to the Recycle Bin (DONE by default for Delete)
* Ctrl + R (or F5)              Refresh the active window (DONE by default)
* Ctrl + Y                      Redo an action (DONE by default)
* Ctrl + Right arrow            Move the cursor to the beginning of the next word (DONE by default)
* Ctrl + Left arrow             Move the cursor to the beginning of the previous word (DONE by default)
* Ctrl + Down arrow             Move the cursor to the beginning of the next paragraph (DONE by default)
* Ctrl + Up arrow               Move the cursor to the beginning of the previous paragraph (DONE by default)
* Ctrl + Alt + Tab              Use the arrow keys to switch between all open apps (DONE by default)
* Alt + Shift + arrow keys      When a group or tile is in focus on the Start menu, move it in the direction specified (No sense)
* Ctrl + Shift + arrow keys     When a tile is in focus on the Start menu, move it into another tile to create a folder (No sense)
* Ctrl + arrow keys             Resize the Start menu when it's open (No sense)
* Ctrl + arrow key  + Spacebar 	Select multiple individual items in a window or on the desktop (DONE by default)
* Ctrl + Shift with an arrow keySelect a block of text (DONE by default)
* Ctrl + Esc                    Open Start (DONE by configuration)
* Ctrl + Shift + Esc            Open Task Manager ((DONE by configuration)
* Ctrl + Shift                  Switch the keyboard layout when multiple keyboard layouts are available (No need)
* Ctrl + Spacebar               Turn the Chinese input method editor (IME) on or off (No need)
* Shift + F10                   Display the shortcut menu for the selected item (DONE by default)
* Shift with any arrow key      Select more than one item in a window or on the desktop, or select text in a document (DONE by default)
* Shift + Delete                Delete the selected item without moving it to the Recycle Bin first (No need)
* Right arrow                   Open the next menu to the right, or open a submenu (DONE by default)
* Left arrow                    Open the next menu to the left, or close a submenu (DONE by default)
* Esc                           Stop or leave the current task (DONE by default)

#### Windows logo key keyboard shortcuts

* Windows logo key  	                Open or close Start (DONE by configuration)
* Windows logo key  + B 	            Set focus in the notification area (DONE by configuration)
* Windows logo key  + Shift + C         Open the charms menu (Do nothing visible)
* Windows logo key  + D 	            Display and hide the desktop (DONE by configuration)
* Windows logo key  + Alt + D 	        Display and hide the date and time on the desktop (Not Useful)
* Windows logo key  + E 	            Open File Explorer (Done by configuration)
* Windows logo key  + F 	            Open Feedback Hub and take a screenshot (Not Useful)
* Windows logo key  + G 	            Open Game bar when a game is open (Not Useful)
* Windows logo key  + H 	            Start dictation (Not Useful)
* Windows logo key  + I 	            Open Settings (DONE by configuration)
* Windows logo key  + J                 Set focus to a Windows tip when one is available. (Not Useful)
* Windows logo key  + K 	            Open the Connect quick action (Not Useful)
* Windows logo key  + L 	            Lock your PC or switch accounts (DONE by default)
* Windows logo key  + M 	            Minimize all windows (DONE by configuration)
* Windows logo key  + O 	            Lock device orientation (Not Useful)
* Windows logo key  + P 	            Choose a presentation display mode (Not Useful)
* Windows logo key  + R 	            Open the Run dialog box (DONE)
* Windows logo key  + S 	            Open search (DONE by configuration)
* Windows logo key  + T 	            Cycle through apps on the taskbar (No sense without taskbar)
* Windows logo key  + U 	            Open Ease of Access Center (Not Useful)
* Windows logo key  + V 	            Cycle through notifications (Not Useful)
* Windows logo key  + Shift + V         Cycle through notifications in reverse order (Not Useful)
* Windows logo key  + X 	            Open the Quick Link menu (DONE by Configuration)
* Windows logo key  + Y 	            Switch input between Windows Mixed Reality and your desktop (Do nothing visible)
* Windows logo key  + Z 	            Show the commands available in an app in full-screen mode (Do nothing visible)
* Windows logo key  + period (.) or semicolon (;)   Open emoji panel (Not Useful)
* Windows logo key  + comma (,)         Temporarily peek at the desktop (Not Useful)
* Windows logo key  + Pause 	        Display the System Properties dialog box (Not Useful)
* Windows logo key  + Ctrl + F 	        Search for PCs (if you're on a network) (Not Useful)
* Windows logo key  + Shift + M         Restore minimized windows on the desktop (Not Useful)
* Windows logo key  + number 	        Open the desktop and start the app pinned to the taskbar in the position indicated by the number. If the app is already running, switch to that app. (No Sense)
* Windows logo key  + Shift + nbr       Open the desktop and start a new instance of the app pinned to the taskbar in the position indicated by the number (No Sense without taskbar)
* Windows logo key  + Ctrl + nbr        Open the desktop and switch to the last active window of the app pinned to the taskbar in the position indicated by the number (No Sense without taskbar)
* Windows logo key  + Alt + nbr         Open the desktop and open the Jump List for the app pinned to the taskbar in the position indicated by the number (No Sense without taskbar)
* Windows logo key  + Ctrl + Shift + nbr    Open the desktop and open a new instance of the app located at the given position on the taskbar as an administrator (No Sense without taskbar)
* Windows logo key  + Tab               Open Task view (Not Useful)
* Windows logo key  + Up arrow          Maximize the window (DONE)
* Windows logo key  + Down arrow        Remove current app from screen or minimize the desktop window (DONE)
* Windows logo key  + Left arrow        Maximize the app or desktop window to the left side of the screen (DONE)
* Windows logo key  + Right arrow       Maximize the app or desktop window to the right side of the screen (DONE)
* Windows logo key  + Home 	            Minimize all except the active desktop window (restores all windows on second stroke) (Not Useful)
* Windows logo key  + Shift + Up arrow 	Stretch the desktop window to the top and bottom of the screen (Not Useful)
* Windows logo key  + Shift + Down arrow    Restore/minimize active desktop windows vertically, maintaining width (Not Useful)
* Windows logo key  + Shift + Left arrow or Right arrow 	Move an app or window in the desktop from one monitor to another (Not Useful)
* Windows logo key  + Spacebar          Switch input language and keyboard layout (Not Useful)
* Windows logo key  + Ctrl + Spacebar   Change to a previously selected input (Not Useful)
* Windows logo key  + Ctrl + Enter      Open Narrator (Do nothing visible)
* Windows logo key  + Plus (+)          Open Magnifier (Do nothing visible)
* Windows logo key  + forward slash (/) Begin IME reconversion (Do nothing visible)
* Windows logo key  + Ctrl + V          Open shoulder taps (Do nothing visible)

#### Virtual desktops keyboard shortcuts
* Windows logo key  + Tab                 Open Task view (DONE by configuration)
* Windows logo key  + Ctrl + D            Add a virtual desktop (Not Useful)
* Windows logo key  + Ctrl + Right arrow  Switch between virtual desktops you’ve created on the right (DONE by configuration)
* Windows logo key  + Ctrl + Left arrow   Switch between virtual desktops you’ve created on the left (DONE by configuration)
* Windows logo key  + Ctrl + F4           Close the virtual desktop you're using (Not Useful)
