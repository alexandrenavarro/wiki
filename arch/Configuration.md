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

## Post Installation if you come from debian-standard

    sudo pacman -S firefox-esr bspwm sxhkd zsh

## Window Manager : Bspwm

    sudo pacman -S bspwm
    mkdir -p ~/.config/bspwm
    cd ~/.config/bspwm
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/bspwm/bspwmrc
    chmod a+x bspwmrc
    
## Hot Key daemon : sxhkd

    sudo pacman -S sxhkd
    mkdir -p ~/.config/sxhkd
    cd ~/.config/sxhkd
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/sxhkd/sxhkdrc
    

## Launcher
    
    sudo pacman -S rofi


## Wallpaper Manager

    sudo pacman -S feh
    
## Theme

    sudo apt install ttf-ubuntu-font-family lxappearance

On Widget, set Adwaita-dark and DefaultFont Ubuntu 11

On Other, set Toolbar Style Icons only and Small toolbar icon
    
    sudo apt install qt5ct
 
 On Appearance, Set Adwait-dark
 
 Add in your .profile or .bashrc
 
    export QT_QPA_PLATFORMTHEME="qt5ct"
 
 It seems working on quasi all qt applications, only menu in cura are not themed.
 
 See https://wiki.manjaro.org/index.php/Set_all_Qt_app%27s_to_use_GTK%2B_font_%26_theme_settings
 


# Software Installation

## From pacman 

### Update packages

    sudo pacman -Syu
    
Set an france miro

    ## France
    Server = http://mir.archlinux.fr/$repo/os/$arch

### Install package

    sudo pacman -S git

### Remove package
    
    sudo pacman -Rns git

### Clean package cache

    pacman -Sc
    
### Clean obsolete package

    sudo pacman -Rns $(pacman -Qqdt)
    

## From yay

    pacman -S --needed git base-devel
    git clone https://aur.archlinux.org/yay.git
    cd yay
    makepkg -si


### Accessories


#### Archive Manager
    
    sudo pacman -S file-roller
   

#### Pdf Document Viewer
    
    sudo pacman -S zathura atril

Adopted : zathura (low memory, simple)

Adopted (for printing) : atril (basic menu + print correctly)

Tested but not selected : onkular (too many dependency to qt).

Tested but not selected : evince (same me but does not have real menu bar, hide some polybar info on the right)
    
    
#### Menu for launcher
    
    sudo pacman -S alacarte
    
Example Config for a terminal app with alacritty terminal.
    
    alacritty --class lf -t lf -e lf

### Education

#### Typing Learning
    
    sudo pacman -S klavaro

### Graphics  

#### Image Viewer
    
    sudo pacman -S sxiv feh eog shotwell
    
Adopted sxiv : faster to open, cool shortcuts (miss just to print the image, add sxiv.sh to navigate easily in the picture of a directory)

Adopted just for wallpaper : feh

Adopted as second choice just for printing quickly : eog

Adopted for manipulating image : shotwell

#### Image Manager (if you want to classify your pictures)
    
    sudo pacman -S  digikam 
    
#### 3D Modeling Printing

    sudo pacman -S cura
    
### Internet

#### Web Browser

Brave
    yay -S brave-bin
    
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

Firefox / Tor Browser
    
    sudo pacman -S firefox wget curl
    sudo pacman -S torbrowser-launcher
    
    
#### Torrent Client

    sudo pacman -S transmission-gtk transmission-cli

#### Mail Client
    
Use directly webclient like gmail with 
    
    brave --new-window --app=https://gmail.com/
    
    
#### Chat

    yay -S slack-desktop
    
    
### Office
    
    sudo pacman -S libreoffice-fresh-fr
    sudo pacman -S csvkit

#### Ascidoctor

    sudo pacman -S asciidoctor
    yay -S asciidoctor-pdf
    
    asciidoctor -r asciidoctor-pdf -b pdf file.adoc
    
#### Markdown

    sudo apt install pandoc texlive-core
    pandoc -o dest.pdf source.md
    
#### Book Manager (if you use kindle)
    
    sudo pacman -S calibre    
    

### Development 

#### File Editor
    
    sudo pacman -S micro
    sudo yay -S visual-studio-code-bin
    
Adopted : micro (memory 30mo, have terminal mode, classical keyshortcuts)

Adopted only to build Marlin with Platformio plugin : vscode (really slow to start at least 2-3 s on my machine, take >100mo, )

Tested but not selected : geany (not bad at all but I prefer micro, low memory for non terminal 60mo, start fast)


#### JVM    
   
    sudo pacman -S jdk-openjdk kotlin maven gradle 
    
#### IDE    
    sudo pacman -S intellij-idea-community-edition
    sudo yay -S  intellij-idea-ultimate-edition



### Multimedia

#### Video Player
    
    sudo pacman -S mpv

Adopted : mpv (only video, light)

Tested but not adopted : vlc (have menu)

#### Music Player
    
    sudo pacman -S moc

Adopted : moc (terminal music player)

Tested but not adopted : audacious (more memory)

Tested but not adopted : clementine (more memory)

Tested but not adopted : rhythmnbox (more memory)

#### DVD Ripper
    
    sudo pacman -S handbrake

#### DVD Burner
    
    sudo pacman -S brasero
    
#### Audio Controller 
    sudo pacman -S pulseaudio pulseaudio-bluetooth pulseaudio-alsa pavucontrol volumeicon blueman
    

### System / Utilities
    
    sudo pacman -S xdotool fdupes git jq unrar p7zip exfat-utils renameutils odt2txt catdoc bat fzf fd libnotify entr skim bat lsd
    
#### Finder

    sudo pacman -S  fd
    
#### Fuzzy Finder    
    
    sudo pacman -S skim
    
Usefull command with fzf
    
    xdg-open $(sk --preview 'cat {}')
    micro $(sk --preview 'cat {}')
       


#### File Explorer
    
    sudo pacman -S thunar thunar-archive-plugin
    yay -S lf-bin

Adopted : lf (terminal), 
find a way smb/dav not manage by default (just a bash script).

Adopted (second choice) : thunar.

Tested but not selected : nautilus (navigation with keys less easy than thunar)

#### Terminal
    
    sudo pacman -S alacritty rxvt-unicode
    
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

    sudo pacman -S zsh
    
    
Theme

Install first a font manager, che

    sudo apt install font-manager
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.zsh/powerlevel10k
    echo 'source ~/.zsh/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
    mkdir -p ~/.fonts
    cd ~/.fonts
    wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf
    wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf
    wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf
    wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf
    
    
Caution you have to install also the recommanded MesloLGS NF Regular font.

Configure your powerlevel10k

    p10k configure
    
Configure the font in your (ex in for rxvt in .XResources)

URxvt.font: xft:MesloLGS NF:size=11

Configure your zsh shell as the default one

    chsh -s $(which zsh)

Plugins

    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.zsh/zsh-syntax-highlighting
    git clone https://github.com/zsh-users/zsh-history-substring-search.git ~/.zsh/zsh-history-substring-search
    git clone https://github.com/zsh-users/zsh-completions.git ~/.zsh/zsh-completions
    git clone https://github.com/MichaelAquilina/zsh-auto-notify.git ~/.zsh/zsh-auto-notify
    git clone https://github.com/MichaelAquilina/zsh-you-should-use.git ~/.zsh/zsh-you-should-use
    git clone https://github.com/changyuheng/zsh-interactive-cd.git ~/.zsh/zsh-interactive-cd

See my .zshrc file.


#### Monitor
    
    sudo pacman -S htop

Adopted htop : fast, low memory usage and customizable

Tested but not selected gnome-monitor-systeme : use more memory, less information

Tested but not selected mate-monitor-system : use more memory, less information

#### System Tray

    sudo pacman -S htop

Adopted polybar : works quasi-perfectly with transparency.

Tested trayer but not select : problem transparency

Tested stanfolonetray but not select : problem transparency


#### Notification

    sudo pacman -S dunst
    
Adopted : dunst (simple)
See https://wiki.archlinux.org/index.php/Desktop_notifications dunst or Deadd Notification Center 


#### Disks
    
    sudo pacman -S baobab gnome-disk-utility udiskie ncdu
    
    
#### Flash ISO on usb stick

    yay -S balena-etcher    

#### Screen Management

    sudo pacman -S arandr
    
#### Webcam

    sudo pacman -S cheese

#### Scanner
    
    sudo pacman -S simple-scan

Adopted simple-scan : works, no concurrency.
    
#### Printer Server

    sudo pacman -S cups system-config-printer
    
   
### Preferences / Control Center
    
    sudo pacman -S lxappearance qt5ct

#### Login 
    
    sudo pacman -S lightdm

#### Lock
    
    sudo pacman -S light-locker
    
#### Panel Bar (optional)
    
    yay -S polybar

Tested but not selected polybar : moving window with openbox works, higly customisable, transparency but finally no need.

Tested but not selected tint2 : size for moving window with openbox does not any work with %    
    
#### Font 
    
    sudo pacman -S deepin-font-manager
    sudo pacman -S  ttf-ubuntu-font-family

#### Bluetooth (if needed)
    
    sudo pacman -S blueman 



    
# Custom Configuration / Installation for some applications
   
## Feh (Wallpaper)
    
    sudo pacman -S feh
    cd ~/.config/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/wallpaper.png

## Polybar (optional)
    
    sudo pacman -S fonts-ubuntu fonts-material-design-icons-iconfont
    yay -S ttf-material-design-icons 
    yay -S polybar 
    mkdir ~/.config/polybar
    cd ~/.config/polybar
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/polybar/config

See the resolution of bug for tray icon transparency https://github.com/polybar/polybar/issues/913

## Picom (optional)
    
    sudo pacman -S picom

Needed if you want to have transparency window notably for polybar.

## Lightdm
    
    sudo pacman -S lightdm
    sudo pacman -S light-locker
    
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
    
    sudo pacman -S alacarte
    
Add Items 
Lock : dm-tool lock
Shutdown : systemctl poweroff
Restart : systemctl reboot
Logout : bspc quit

It will add in ~/.local/share/applications/xxx.desktop files you can customize.

## Conky (optional)
If it works

    sudo pacman -S conky
    
else
    
    cd Applications
    curl -sL -o conky-x86_64.AppImage $(curl -sL https://api.github.com/repos/brndnmtthws/conky/releases/latest | jq --raw-output '.assets[0] | .browser_download_url')
    chmod +x ./conky-x86_64.AppImage
    ./conky-x86_64.AppImage -C > ~/.conkyrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.conkyrc

## Sxiv

    sudo pacman -S sxiv
    cd ~/bin/
    wget https://raw.githubusercontent.com/alexandrenavarro/scripts/main/sxiv.sh
    chmod +x sxiv.sh    

## Rxvt
   
    sudo pacman -S rxvt-unicode
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
    
    yay -S lf-bin
    sudo pacman -S mediainfo highlight

### Configuration
    
    mkdir -p .config/lf
    cd .config/lf
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/lfrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/preview.sh
    chmod a+x preview.sh
    
    
Remote Commands 
    lf -remote 'send updir'
	lf -remote 'send set ratios 1:2'
	lf -remote 'send open'
	lf -remote 'send set ratios 1:2:3'


    

## diskie (automount of usb drive)
    
    sudo pacman -S udiskie    
    
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
    
    sudo pacman -S micro
    mkdir -p ~/.config/micro/
    cd ~/.config/micro
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/binding.json
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/settings.json

See select Next/Previous Paragraph https://github.com/zyedidia/micro/issues/1968

Don't know why but just Ctrl+Shift+Left in rxvt works as Ctrl+Left (works in mate-terminal).


    
## moc
    
    sudo pacman -S moc
    mkdir -p ~/.moc/themes/
    cd ~/.moc/themes/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/themes/kiss_theme
    cd ~/.moc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/config
    
## Lsd
    
    sudo pacman -S lsd
    mkdir -p ~/.config/lsd
    cd ~/.config/lsd
     wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lsd/config.yaml
    

## Intellij

### Installation

    sudo pacman -S intellij-idea-community-edition

### Configuration

If you use bspwm, add 
    
    export _JAVA_AWT_WM_NONREPARENTING=1

to launch just after comment # Run the IDE.

    sudo micro /usr/share/idea/bin/idea.sh

Change some shorcuts
* Editor Actions | Move Caret to Paragraph : CTRL + UP / Down (equivalent)
* Main menu | Navigate | Search Everywhere : CTRL + L (in addition of Shift / Shift)
* Main menu | Navigate | Back : Alt + Left (in addition of ALT + CTRL + Left)
* Main menu | Navigate | Forward : Alt + Right (in addition of ALT + CTRL + Right)
* Main menu | Navigate | Go to Implementation : Shift + F4
* Main menu | Tool Window | Project : Alt + Shift + "
* Main menu | Edit | Find Usages | Find Usages : Ctrl + F3 (in addition of Alt + F7)
* Main menu | Code | Code Completion : Complete Code Statement : Ctrl + Enter (in addition of Ctrl + Shift + Enter)
* Tools Windows | Terminal : F12 (it removes possibility to use last window tool but I don't used)


## Grub

    sudo pacman -S grub-customizer

Use Grub Customizer to set the different settings you want, save and install to mbr.
Be sure your mbr you changed is the one launched by the motherboard (or re-set in the bios) notably if you installed another linux distribution on another disk drive.

You can also change the configuration int /etc/default/grub and update grub.

    sudo update-grub
    
# Printer/Scanner

## Installation

TODO 
    sudo pacman -S cups system-config-printer
    
Add rights to your user (voir https://wiki.debian.org/CUPSPrintQueues?action=show&redirect=PrintQueuesCUPS#webinterface)
    
    usermod -a -G lpadmin yourusername
    
And go to to configure your printer http://localhost:631/admin or use 
Install the one with driverless



# Laptop specific

## Auto-cpu freq

TODO

https://github.com/AdnanHodzic/auto-cpufreq


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

