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


# Installation
Download debian-standard with non-free (here 10)  and then update to testing (11) if you want to have update up-to-date softwares


# Post Installation

## Post Installation if you come from debian-standard
    su
    sudo adduser anavarro sudo

You have to logout and login.

    sudo apt install firefox-esr lightdm bspwm sxhkd

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

## Window Manager : Bspwm

    sudo apt install bspw
    mkdir -p ~/.config/bspwm
    cd ~/.config/bspwm
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/bspwm/bspwmrc
    chmod a+x bspwmrc
    
## Hot Key daemon : sxhkd

    sudo apt install sxhkd
    mkdir -p ~/.config/sxhkd
    cd ~/.config/sxhkd
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/sxhkd/sxhkdrc
    

### Installation of software started with bspwm session

    sudo apt install feh compton sxhkd
    
#### Theme

    sudo apt install fonts-ubuntu lxappearance

On Widget, set Adwaita-dark and DefaultFont Ubuntu 11

On Other, set Toolbar Style Icons only and Small toolbar icon
    
    sudo apt install qt5ct
 
 On Appearance, Set Adwait-dark
 
 Add in your .profile or .bashrc
 
    export QT_QPA_PLATFORMTHEME="qt5ct"
 
 It seems working on quasi all qt applications, only menu in cura are not themed.
 
 See https://wiki.manjaro.org/index.php/Set_all_Qt_app%27s_to_use_GTK%2B_font_%26_theme_settings
 

### Keyboard Layout
If after the start of bspwm the layout is not correct (compared to the one in login manager), check throught bar / keyboard layout manager is correctly set with Bus Preference notably

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

Adopted only to build Marlin with Platformio plugin : vscode (really slow to start at least 2-3 s on my machine, take >100mo, )

Tested but not selected : geany (not bad at all but I prefer micro, low memory for non terminal 60mo, start fast)


#### Archive Manager
    
    sudo apt install file-roller
    
#### Window Compositor (optional)
    
    sudo apt install compton


#### Pdf Document Viewer
    
    sudo apt install zathura

Adopted : zathura (low memory, simple)

Tested but not select : atril (basic menu)

Tested but not selected : onkular (too many dependency to qt).

Tested but not selected : evince (same me but does not have real menu bar, hide some polybar info on the right)
    
    
#### Menu for launcher
    
    sudo apt install alacarte
    
Example Config for a terminal app with alacritty terminal.
    
    alacritty --class lf -t lf -e lf

### Education

#### Typing Learning
    
    sudo apt install klavaro

### Graphics  

#### Image Viewer
    
    sudo apt install sxiv
    sudo apt install feh
    sudo apt install eog
    sudo apt install shotwell
    
Adopted sxiv : faster to open, cool shortcuts (miss just to print the image, add sxiv.sh to navigate easily in the picture of a directory)

Adopted just for wallpaper : feh

Adopted as second choice just for printing quickly : eog

Adopted for manipulating image : shotwell

#### Image Manager (if you want to classify your pictures)
    
    sudo apt install digikam 
    
### Internet

#### Web Browser

Brave

    sudo apt install apt-transport-https curl
    sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
    echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
    sudo apt update
    sudo apt install brave-browser
    
Plugins
* CrxMouse
* Pocket
* Vimium : use this cs for links

Use

div > .vimiumHintMarker {
/* linkhint boxes */
background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#565756),
color-stop(100%,#242524));
border: 1px solid #e4e5e4;
opacity: 1.0;
text-shadow: none !important;
}

div > .vimiumHintMarker span {
/* linkhint text */
color: #f1f2f1;
font-weight: normal;
font-size: 18px;
font-family: Avenir;
}

div > .vimiumHintMarker > .matchingCharacter {
color: #969696;
}


Configuration
In brave://flags/ set dark to true

Firefox / Chromium
    
    sudo apt install firefox-esr wget curl
    sudo apt install chromium 
    
#### Torrent Client

    sudo apt install transmission transmission-cli

#### Mail Client
    
Use directly webclient like gmail with 
    
    brave-browser --new-window --app=https://gmail.com/
    
### Office
    
    sudo apt install libreoffice
    sudo apt install csvkit
    
    sudo apt install asciidoctor
    sudo gem install asciidoctor-pdf
    
    asciidoctor -r asciidoctor-pdf -b pdf file.adoc
    

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
    
    
### Utilities   
    
    sudo apt install cargo policykit-1-gnome xdotool fdupes git jq unrar-free p7zip exfat-utils exfat-fuse rename odt2txt catdoc exif bat fzf autojump fd-find arc bsdmainutils libnotify entr
    cargo install skim bat lsd 
    
#### Finder

    sudo apt install fd-find
    
#### Fuzzy Finder    
    
    cargo install skim
    
Usefull command with fzf
    
    xdg-open $(sk --preview 'cat {}')
    micro $(sk --preview 'cat {}')
    
TODO skim (just tar to unzip closed to fzf), as-tree just launch a cargo command, alias to add fdfind    
   

#### Book Manager (if you use kindle)
    
    sudo apt install calibre

### System Tools
    
    sudo apt install cargo

#### File Explorer
    
    sudo apt install thunar thunar-archive-plugin

Adopted : lf (terminal), 
find a way smb/dav not manage by default (just a bash script).

Adopted (second choice) : thunar.

Tested but not selected : nautilus (navigation with keys less easy than thunar)

#### Terminal
    
    sudo apt install rxvt-unicode
    
Requirements by order of priority :
* Fast (less than 500 ms to start) and fast to write output and readinput (no latency detected).
* These shortcuts in micro must work :
  * navigate : home, left, down, up, right, end, ctrl+Left, ctrl+down, ctrl+up, ctrl+right, ctrl+home, ctrl+end.
  * selection : shift+home, shift+left, shift+down, shift+up, shift+right, shift+end, shift+ctrl+Left, shift+ctrl+down, shift+ctrl+up(optional), shift+ctrl+right(optional), shift+ctrl+home(optional), shift+ctrl+end (optional).
* These shortcuts in terminal (use `showkeys -a` and `bindkey -M emacs` bindkey to solve it like `bindkey '^[[1;5D'  backward-word`) : home, ctrl+Left, ctrl+right, end, shift+home ctrl+x, shift+ctrl+left ctrl+x, shift+ctrl+right ctrl+x, shift+end ctrl+x
* Working Copy / Paste without mouse :
  *  from external app (ctrl+c) to command line (ctrl+shift+v or equivalent)
  *  from commandline (cppath, cpfile, cpbuffer) to external app (ctrl+v)
  *  from micro (ctrl+c) to external app (ctrl+v)
  *  from external app (ctrl+c) to micro (ctrl+v)
  *  from selection of the output (what ever) to external app (ctrl+v), a select mode
* Must work with lf notably with the script to preview or unpreview base if lf is focus or not.
* True color for previewing image through chafa in more color (optional)
* Lightweight as possible in memory (optional)

Not required at all :
* tabs (I used a tiling window manager)
* layout management (I used a tiling window manager)


Adopted alacritty : faster, shortcuts ok, copy/paste ok, lf ok, have true color but no so lightweight in memory (80-100mo)

Adopted previously rxvt : fast, shortcuts ok with config,  works well with lf, low memory usage of any other terminal but have some trouble with copy/paste (copy from external app, select mode), no true color (10-20mo)

To retest : kitty.
Tested but not selected choice : ssterm, faster and low memory usage but need to recompile to add some feature, some Shift+End / Shift+Home does not work by default with micro.

Tested but not selected choice : mate-terminal : more memory but all the binding in micro work well.

Tested but not selected gnome-mate-terminal : very close to mate-terminal without transparency (40 mo)

#### Shell

Installation of the zsh shell

    sudo apt install zsh
    
Installation of plugins manager of zsh : Antigen

    curl -L git.io/antigen > antigen.zsh
    
Theme

Use romkatv/powerlevel10k

Caution you have to install also the recommanded MesloLGS NF Regular font.

Configure your powerlevel10k

    p10k configure
    
Configure the font in your (ex in for rxvt in .XResources)

URxvt.font: xft:MesloLGS NF:size=11

Configure your zsh shell as the default one

    chsh -s $(which zsh)

Plugins

See my .zshrc file.


#### Launcher
    
    sudo apt install rofi

Adopted rofi : very fast and manage window selection.

#### Monitor
    
    sudo apt install htop

Adopted htop : fast, low memory usage and customizable

Tested but not selected gnome-monitor-systeme : use more memory, less information

Tested but not selected mate-monitor-system : use more memory, less information

#### System Tray
Adopted polybar : works quasi-perfectly with transparency.

Tested trayer but not select : problem transparency

Tested stanfolonetray but not select : problem transparency


#### Notification
TODO Test dunst or Deadd Notification Center ?
See https://wiki.archlinux.org/index.php/Desktop_notifications dunst or Deadd Notification Center 


#### Disks
    
    sudo apt install baobab gnome-disk-utility udiskie ncdu 
    cargo install diskonaut

#### Screen Management

    sudo apt install arandr
    
#### Webcam To

    sudo apt install cheese

#### Scanner
    
    sudo apt install simple-scan

Adopted simple-scan : works, no concurrency.
    
#### Printer Server

    sudo apt install cups system-config-printer
   
### Preferences / Control Center
    
    sudo apt install lxappearance qt5ct

### Login 
    
    sudo apt install lightdm

### Lock
    
    sudo apt install light-locker
    
### Panel Bar (optional)
    
    sudo apt install polybar

Tested but not selected polybar : moving window with openbox works, higly customisable, transparency but finally no need.

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

## Polybar (optional)
    
    sudo apt install fonts-ubuntu fonts-material-design-icons-iconfont
    sudo apt install polybar
    mkdir ~/.config/polybar
    cd ~/.config/polybar
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/polybar/config

See the resolution of bug for tray icon transparency https://github.com/polybar/polybar/issues/913

## Compton (optional)
    
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
Logout : bspc quit

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

## Sxiv

    sudo apt install sxiv
    cd ~/Applications/
    wget https://raw.githubusercontent.com/alexandrenavarro/scripts/main/sxiv.sh
    chmod +x sxiv.sh    

## Rxvt
   
    sudo apt install rxvt-unicode
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.Xresources
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.inputrc
   
Useful to understand how the terminal manages different keys, use 

    cat -v
    
or
   
    showkey -a
    
or in micro, activate raw mode 

    raw
   
## Lf

### Installation
Download the package and install in Applications
    
    sudo apt install mediainfo highlight

### Configuration
    
    mkdir -p .config/lf
    cd .config/lf
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/lfrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/preview.sh
    chmod a+x preview.sh
    
    
TODO
Remote Commands 
    lf -remote 'send updir'
	lf -remote 'send set ratios 1:2'
	lf -remote 'send open'
	lf -remote 'send set ratios 1:2:3'


    

## diskie (automount of usb drive)
    
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
    xdg-mime default micro.desktop application/javascript
    xdg-mime default micro.desktop application/xml

    

Image Viewer : jpg/png/gif -> default sxiv

    xdg-mime default sxiv.desktop image/jpeg
    xdg-mime default sxiv.desktop image/png
    xdg-mime default sxiv.desktop image/gif
    xdg-mime default sxiv.desktop image/bmp

Document Viewer : pdf -> org.pwmt.zathura-pdf-poppler.desktop

    xdg-mime default org.pwmt.zathura-pdf-poppler.desktop application/pdf
    
Compressed files : zip,tar.gz -> file-roller

    xdg-mime default org.gnome.FileRoller.desktop application/zip
    xdg-mime default org.gnome.FileRoller.desktop application/x-compressed-tar
  
Videos : avi,mkv,mp4

    xdg-mime default mpv.desktop video/x-msvideo 
    xdg-mime default mpv.desktop video/x-matroska
    

## Micro
    
    sudo apt install micro
    mkdir -p ~/.config/micro/
    cd ~/.config/micro
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/binding.json
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/settings.json

See select Next/Previous Paragraph https://github.com/zyedidia/micro/issues/1968

Don't know why but just Ctrl+Shift+Left in rxvt works as Ctrl+Left (works in mate-terminal).

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
    
### Lsd
    
    cargo install lsd
    mkdir -p ~/.config/lsd
    cd ~/.config/lsd
     wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lsd/config.yaml

## Etcher
Download AppImage of Etcher, add alacarte and run it.

## Intellij

### Configuration
Add export _JAVA_AWT_WM_NONREPARENTING=1 in the script where you launch intellij if you use bspwm.

Change some shorcuts
* Editor Actions | Move Caret to Paragraph : CTRL + UP / Down (equivalent)
* Main menu | Navigate | Search Everywhere : CTRL + L (in addition of Shift / Shift)
* Main menu | Navigate | Back : Alt + Left (in addition of ALT + CTRL + Left)
* Main menu | Navigate | Forward : Alt + Right (in addition of ALT + CTRL + Right)
* Main menu | Navigate | Go to Implementation : Shift + F4
* Main menu | Tool Window | Project : Alt + Shift + "
* Main menu | Edit | Find Usages | Find Usages : Ctrl + H (in addition of Alt + F7)
* Main menu | Code | Code Completion : Complete Code Statement : Ctrl + Enter (in addition of Ctrl + Shift + Enter)
* Tools Windows | Terminal : F12 (it removes possibility to use last window tool but I don't used)
* Others | Run Context Configuration : To define (it removes possibility to use last window tool but I don't used)


## Slack

### Installation

    sudo apt update
    sudo apt install snapd
    sudo snap install core

    sudo snap install slack --classic
    
### Configuration

Ajouter dans les menu (alacarte) la commande

    snap run slack


## Visual Studio Code

Just to compile Marlin, you can see https://code.visualstudio.com/docs/setup/linux.

### Install

    wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
    sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
    sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

    sudo apt install apt-transport-https
    sudo apt update
    sudo apt install code # or code-insiders


## Install some webapplication like googlemeet / gmail /google calendar
Download https://webcatalog.app/ and run the .AppImage .


## Grub

    sudo apt install grub-customizer

Use Grub Customizer to set the different settings you want, save and install to mbr.
Be sure your mbr you changed is the one launched by the motherboard (or re-set in the bios) notably if you installed another linux distribution on another disk drive.

You can also change the configuration int /etc/default/grub and update grub.

    sudo update-grub
    
# Printer/Scanner

## Installation
    
    sudo apt install cups system-config-printer
    
Add rights to your user (voir https://wiki.debian.org/CUPSPrintQueues?action=show&redirect=PrintQueuesCUPS#webinterface)
    
    usermod -a -G lpadmin yourusername
    
And go to to configure your printer http://localhost:631/admin or use 
Install the one with driverless




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
