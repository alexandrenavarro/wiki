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


# Installation (through arch iso + archifi install script, harder)
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

    
## Post Installation with Archfi

Download and run archfi installer

    curl -LO matmoul.github.io/archfi
    sh archfi
    
If you have an EFI pc, set your /boot on your efi partition


# Installation (through Calam-Arch-Installer, easier)

Download Calam-Arch-Installer iso.

On partition config, don't forget to create /boot/efi partition (needed on efi generally the case on machine post 2016).

Select only the package needed (on a desktop AMD cpu):
    
    base-devel			# Development tools to 
    xorg-server			# Video Xorg
    xorg-init			# Video Xorg
    xf86-input-libinput		# X Input (keyboard / mouse)
    networkmanager		# Network manager
    grub			# Bootloader utils (grub)
    efibootmgr			# Bootloader utils (efi partition)
    dosfstools			# Bootloader utils (efi partition)
    efitools	                # Bootloader utils (efi partition)
    

Select only if you have an AMD CPU

    amd-ucode
    
Select only if you have an Intel CPU

    intel-ucode    
    
Select only if you have an video card with AMD/ATI GPU
    
    xf86-video-amdgpu
    vulkan-radeon
    lib32-vulkan-radeon
    
Select only if you have an video with NVIDIA GPU
    
    nvidia
    nvidia-util
    libva-vdpau-drive
    nvidia-settings
    
Select only if you have an video card with Intel GPU
    
    vulkan-intel
    libvdpau-va-gl
    libva-intel-driver
    
Select only if you have a laptop with NVIDIA prime system permits to switch from GPU from CPU to external GPU.
    
    nvidia-prime

Select at least one desktop environment (I let mate but it will be remove once bspwm + sxhkd will be installed)
    
    mate
    lightdm
    lightdm-gtk-greeter
    lightdm-gtk-greeter-settings


# Post Installation

## Post Installation (basic packages to have my bspwm environment working)

    sudo pacman -S bspwm sxhkd rofi alacritty zsh xsel micro picom feh dunst udiskie polkit-gnome firefox wget

## Window Manager

### Bspwm

    sudo pacman -S bspwm
    
    mkdir -p ~/.config/bspwm
    cd ~/.config/bspwm
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/bspwm/bspwmrc
    chmod a+x bspwmrc
    
## Hot Key daemon

### Sxhkd

    sudo pacman -S sxhkd
    
    mkdir -p ~/.config/sxhkd
    cd ~/.config/sxhkd
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/sxhkd/sxhkdrc
    

## Launcher

### Rofi
    
    sudo pacman -S rofi

    mkdir -p ~/.config/rofi
    cd ~/.config/rofi
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/rofi/config.rasi

TODO fix font

## Wallpaper Manager

### Feh

    sudo pacman -S feh
    
    cd ~/.config/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/wallpaper.png
    

## Terminal

### Alacritty
    
    sudo pacman -S alacritty
    
    mkdir -p ~/.config/alacritty
    cd ~/.config/alacritty
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/alacritty/alacritty.yml
    
## Shell

###  Zsh

Installation of the zsh shell

    sudo pacman -S zsh xsel
    wget https://github.com/alexandrenavarro/dotfiles/blob/master/.zshrc
    
TODO

TODO copy just on sel on terminal and paste with middle click mouse.


## Editor

### Micro
    
    sudo pacman -S micro
    
    mkdir -p ~/.config/micro/
    cd ~/.config/micro
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/binding.json
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/micro/settings.json

See select Next/Previous Paragraph https://github.com/zyedidia/micro/issues/1968

Don't know why but just Ctrl+Shift+Left in rxvt works as Ctrl+Left (works in mate-terminal).



# Software Package Manager

## Pacman

### Configuration

#### Global

In 
    
    sudo micro /etc/pacman.conf
    
Uncomment

    Color
    TotalDownload = 8

Add
    
    ILoveCandy

#### Mirrors
Set best France mirors

    sudo pacman -S reflector
    reflector --verbose --country France -l 50 -p http --sort rate

Copy the outpout at the beginning of

    sudo micro /etc/pacman.d/mirrorlist

### Update packages

    sudo pacman -Syu

### Install package

    sudo pacman -S git

### Remove package
    
    sudo pacman -Rns git

### Clean package cache

    sudo pacman -Scc
    
### Clean obsolete package

    sudo pacman -Rns $(pacman -Qqdt)
    
### Clean ~/.cache
    
    sudo du -sh ~/.cache/
    rm -rf ~/.cache/*
    
### List packages

### List all packages
    pacman -Q

### List package native
    pacman -Qn

### List package external 
    pacman -Qm
    
    
### Fix problem if there is invalid or corrupted package

    sudo pacman -S archlinux-keyring

## Yay

    pacman -S --needed git base-devel
    git clone https://aur.archlinux.org/yay.git
    cd yay
    makepkg -si
    
    
## SDKMAN

    curl -s "https://get.sdkman.io" | bash


# Software Installation

## Accessories

### Archive Manager

#### File Roller

    sudo pacman -S file-roller
   
### Font Manager

#### Deepin font manager

    sudo pacman -S deepin-font-manager
    sudo pacman -S ttf-ubuntu-font-family ttf-nerd-fonts-symbols

### Menu Manager for launcher

#### Alacarte
    
    sudo pacman -S alacarte
    
Add Items 
Lock : dm-tool lock
Shutdown : systemctl poweroff
Restart : systemctl reboot
Logout : bspc quit

It will add in ~/.local/share/applications/xxx.desktop files you can customize.

Example Config for a terminal app with alacritty terminal.
    
    alacritty --class lf -t lf -e lf

See liste of custom applications
    
    cd ~/.local/share/applications/
   
Ex :
gmail.desktop

    [Desktop Entry]
    Version=1.0
    Type=Application
    Name=Gmail
    GenericName=Gmail
    Exec=brave --new-window --app=https://gmail.com/
    Terminal=false
    StartupWMClass=gmail
    Comment=""    
    

## Education

### Typing Learning

#### Klavaro
    
    sudo pacman -S klavaro

## Graphics  

### Image Viewer

#### Benchmark

Adopted sxiv : faster to open, cool shortcuts (miss just to print the image, add sxiv.sh to navigate easily in the picture of a directory)

Adopted just for wallpaper : feh

Adopted as second choice just for printing quickly : eog

Adopted for manipulating image : shotwell

#### Sxiv / Feh / Eog / Shotwell

    sudo pacman -S sxiv feh eog shotwell
    
    cd ~/bin/
    wget https://raw.githubusercontent.com/alexandrenavarro/scripts/main/sxiv.sh
    chmod +x sxiv.sh
    

### Image Manager (if you want to classify your pictures)

#### Digikam
    
    sudo pacman -S digikam 
    
### Color Picker

#### Gcolor2

    sudo pacman -S gcolor2


### 3D Modeling Printing


#### Cura

    sudo pacman -S cura
    
## Internet

### Web Browser


Adopted : brave : Option to have webapp as application, better dark mode, sure in term of anymous, slower than firefox when a lot of javascript (ex with miro, github review).

Adopted in second chocie : firefox : fast but no option to have webapp as app and worse dark mode.

Adopted as anonyamous navigation : torbrowser for anymous.


#### Brave

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

#### Firefox

    sudo pacman -S firefox wget curl

Plugins
* Gesturefy
* Pocket
* Vimium-FF : use this cs for links
* Adblock
* PWA https://addons.mozilla.org/en-US/firefox/addon/pwas-for-firefox/  https://github.com/filips123/PWAsForFirefox (TODO to be tested)

- Configuration
Go to Menu -> General -> Language and Appearance -> Colors -> Manage Colors
Use the same colors used in brave
* Text : #FFFFFF
* Background : #121212
* Unvisited Links : #A9BBFF
* Visited Links : #A9BBFF
* Override the colors : Always



#### Tor Browser

    sudo pacman -S torbrowser-launcher
    
    
### Torrent Client

#### Transmission

    sudo pacman -S transmission-gtk transmission-cli

### Mail Client

#### Gmail in the browser
    
    mkdir -p ~/.local/share/applications
    cd ~/.local/share/applications
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.local/share/applications/gmail.desktop


### Chat

#### Slack

    yay -S slack-desktop
    
    
### Meeting Client

#### Meet in the browser

    mkdir -p ~/.local/share/applications
    cd ~/.local/share/applications
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.local/share/applications/meet.desktop
    

## Office

### Office editors

#### Libreoffice

    sudo pacman -S libreoffice-fresh-fr
    sudo pacman -S csvkit

### Pdf Document Viewer / Utilities

#### Benchmark

Adopted : zathura (low memory, simple)

Adopted (for printing) : atril (basic menu + print correctly)

Tested but not selected : onkular (too many dependency to qt).

Tested but not selected : evince (same me but does not have real menu bar, hide some polybar info on the right)

#### Zathura / Atril
    
    sudo pacman -S zathura atril pdftk imagemagick
    
Usefull command to reduce size of pdf

    gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf
    
Usefull command to extract one page from a pdf    
    pdftk all.pdf cat 1 output page1.pdf
    
Usefull command to merge multiple pdf/jpg in one
    convert 1.pdf 2.pdf all.pdf

### Markup Language 

#### Ascidoctor

    sudo pacman -S asciidoctor
    yay -S asciidoctor-pdf
    
    asciidoctor -r asciidoctor-pdf -b pdf file.adoc
    
#### Markdown

    yay -S pandoc-bin # instead of sudo pacman -S pandoc because heavy haskell dependency
    sudo pacman -S texlive-core
    
    pandoc -o dest.pdf source.md
    
### Book Manager (if you use kindle)

#### Calibre
    
    sudo pacman -S calibre
    

## Programming 

### File Editor

#### Benchmark

Adopted : micro (memory 30mo, have terminal mode, classical keyshortcuts)

Adopted only to build Marlin with Platformio plugin : vscode (really slow to start at least 2-3 s on my machine, take >100mo, )

Tested but not selected : geany (not bad at all but I prefer micro, low memory for non terminal 60mo, start fast)

#### Micro
    
    sudo pacman -S micro

#### VSCode

    sudo yay -S visual-studio-code-bin
    

### Build tools (through pacman) if only last version needed
   
    sudo pacman -S jdk-openjdk kotlin maven gradle 

### Build tools (through SDKMAN) if specific version needed
    
    sdk install java 17.0.1-open

### IDE

#### Intellij

    sudo pacman -S intellij-idea-community-edition
    
    yay -S intellij-idea-ultimate-edition

If you use bspwm (or many tiling window manager)
    
    export _JAVA_AWT_WM_NONREPARENTING=1

in your .profile or 

    micro ~/.profile
    
to launch just after comment # Run the IDE.

    sudo micro /usr/share/idea/bin/idea.sh

Change some shorcuts
* Editor Actions | Move Caret to Paragraph : Ctrl + Up / Down (add)
* Main menu | Navigate | Search Everywhere : Ctrl + L (in addition of Shift / Shift)
* Main menu | Navigate | Back : Alt + Left (in addition of Alt + Ctrl + Left)
* Main menu | Navigate | Forward : Alt + Right (in addition of Alt + Ctrl + Right)
* Main menu | Navigate | Go to Implementation : Shift + F4
* Main menu | Navigate : Next Highlighted Error : F12 (remove F2)
* Main menu | Navigate : Previous Highlighted Error : Shift+F12 (remove Shift+F2)
* Main menu | Tool Window | Project : Alt + Shift + " (in addition of Alt + 1 does not work, region keyboard layout problem)
* Main menu | Code | Code Completion : Complete Code Statement : Ctrl + Enter (in addition of Ctrl + Shift + Enter)
remove Shift+F2)
* Main menu | Code | Folding : Ctrl + Plus(in addition on Ctrl+Numpad+, does not work with Plus not Numpad+)
* Main menu | Refactor : Rename : F2 (in addition Shift+F6)
* Main menu | Refactor : Refactor : Shift+F2 (in addition Ctrl+Alt+Shift+T or Shift+F12)


### Docker
	
    sudo pacman -S docker
    	
    sudo systemctl start docker.service
    sudo systemctl enable docker.service
    
    sudo usermod -aG docker ${USER}
    sudo chmod 666 /var/run/docker.sock
    
    
### Aws

    yay -S aws-cli-v2-bin
    

### Rest client

#### Postman

    yay -S postman-bin


## Sound & Video

### Audio Controller

#### Pulsaudio / Pavucontrol
    
    sudo pacman -S pulseaudio pulseaudio-alsa pavucontrol volumeicon 


### Video Player

#### Benchmark 

Adopted : mpv (only video, light)

Tested but not adopted : vlc (have menu, many codecs included by default)


#### Mpv
    
    sudo pacman -S mpv
    
#### Vlc     
    sudo pacman -S vlc


### Music Player

#### Benchmark

Adopted : moc (terminal music player)

Tested but not adopted : audacious (more memory)

Tested but not adopted : clementine (more memory)

Tested but not adopted : rhythmnbox (more memory)


#### Moc
    sudo pacman -S moc
    
    mkdir -p ~/.moc/themes/
    cd ~/.moc/themes/
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/themes/kiss_theme
    cd ~/.moc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.moc/config    


### DVD Ripper

#### MakeMkv 

    yay -S makemkv
    
#### Handbrake
    
    sudo pacman -S handbrake

### CD/DVD Burner

#### Brasero
    
    sudo pacman -S brasero
    
### Webcam

#### Cheese

    sudo pacman -S cheese
    

## System Tools / Utilities / Other

### Finder

#### Fd

    sudo pacman -S  fd
    
### Fuzzy Finder

#### Skim
    
    sudo pacman -S skim
    
Usefull command with fzf
    
    xdg-open $(sk --preview 'cat {}')
    micro $(sk --preview 'cat {}')
    
### File Lister

#### Lsd

    sudo pacman -S lsd
    
    mkdir -p ~/.config/lsd
    cd ~/.config/lsd
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lsd/config.yaml
    
       
### Some useful command lines

    sudo pacman -S xdotool fdupes git jq unrar p7zip exfat-utils renameutils odt2txt catdoc bat fzf fd libnotify entr skim mediainfo highlight xorg-xkill github-cli
    

### File Explorer

#### Benchmark

Adopted : lf (terminal), 
find a way smb/dav not manage by default (just a bash script).

Adopted (second choice) : thunar.

Tested but not selected : nautilus (navigation with keys less easy than thunar)

#### Lf
    yay -S lf-bin
    
    mkdir -p .config/lf
    cd .config/lf
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/lfrc
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/lf/preview.sh
    chmod a+x preview.sh

#### Thunar

    sudo pacman -S thunar thunar-volman thunar-archive-plugin thunar-media-tags-plugin polkit-gnome
	

TODO problem mount network explorer

### Terminal

#### Benchmark

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


Useful to understand how the terminal manages different keys, use 

    cat -v
    
or
   
    showkey -a
    
or in micro, activate raw mode 

    raw
    
#### Alacritty
    
    sudo pacman -S alacritty
    
    mkdir -p ~/.config/alacritty
    cd ~/.config/alacritty
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/alacritty/alacritty.yml    
    
#### Rxvt (optional)

    sudo pacman -S rxvt-unicode
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.Xresources
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.inputrc
   


### Shell

#### Zsh

Installation of the zsh shell

    sudo pacman -S zsh xsel


Theme

Install first a font manager, che

    sudo pacman -S deepin-font-manager
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
wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.zshrc


### Monitor

#### Benchmark

Adopted htop : fast, low memory usage and customizable

Alternative btop : fast, low memory usage and customizable

Tested but not selected gnome-monitor-systeme : use more memory, less information

Tested but not selected mate-monitor-system : use more memory, less information


#### Htop
    
    sudo pacman -S htop
    
#### Btop
    
    sudo pacman -S btop 
    
#### Bashtop
    
    sudo pacman -S bashtop        



### Notification

#### Dunst

    sudo pacman -S dunst
    
Adopted : dunst (simple)

### Disks
    
    sudo pacman -S ncdu baobab gnome-disk-utility udiskie 
    sudo pacman -S gvfs gvfs-gphoto2 gvfs-mtp gvfs-nfs gvfs-smb ntfs-3g exfat-utils samba smbclient
    
Some specific mount

    sudo pacman -S gvfs gvfs-afc     // apple 
    sudo pacman -S gvfs gvfs-goa     // gnome cloud storage
    sudo pacman -S gvfs gvfs-google  // goodle cloud storage
    sudo pacman -S gvfs gvfs-gphoto2 // digitial camera
    sudo pacman -S gvfs gvfs-mtp     // android phone
    sudo pacman -S gvfs gvfs-nfs     // nfs
    sudo pacman -S gvfs gvfs-smb     // samba
    sudo pacman -S ntfs-3g           // ntfs
    sudo pacman -S exfat-utils       // exfat
    sudo pacman -S gvfs-obexftp      // bluetooth

TODO check in tunar (network / phone mount)
    
### Flash ISO on usb stick

#### Etcher

    yay -S balena-etcher
   
## Others (Preferences / Control Center)

   
### Theme
    
    sudo pacman -S ttf-ubuntu-font-family lxappearance gnome-themes-extra

On Widget, set Adwaita-dark and DefaultFont Ubuntu 11

On Other, set Toolbar Style Icons only and Small toolbar icon
    
    sudo pacman -S qt5ct
    yay -S adwaita-qt
 
 On Appearance, Set Adwait-dark
 
 Add in your .profile or .bashrc
 
    export QT_QPA_PLATFORMTHEME="qt5ct"

### Login / Lock
    
    sudo pacman -S lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings
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

### Network Manager

    sudo pacman -S networkmanager nm-applet networkmanager-openvpn

### Screen Management

#### Arandr (optional)

    sudo pacman -S arandr
    
TODO script to detect if multiple output are availabe, use the external screen


### Hardware Info

#### Inxi

    yay -S inxi

### Printer (optional)

    sudo pacman -S simple-scan cups system-config-printer
    
    yay -S epson-inkjet-printer-escpr2
    
    sudo gpasswd -a $LOGNAME lp 
    
    systemctl start cups.service
    systemctl enable cups.service

### Scanner (optional)

#### Scanner Epson ET-4750

    yay epson-inkjet-printer-escpr2
    yay imagescan-plugin-networkscan
    sudo pacman -S imagescan
    yay imagescan-plugin-networkscan

It works on usb but it does not work on network, I don't know why.
We should edit the file /etc/utsushi/utsushi.conf with

dev2.udi    = esci:networkscan://192.168.0.6:1865
dev2.model  = ET-4750 (Network)
dev2.vendor = EPSON

See https://www.ordinatechnic.com/distribution-specific-guides/Arch/installing-an-epson-multifunction-printer-on-arch-linux-and-derivatives

### System Tray / Panel Bar (optional)

#### Benchmark

Adopted polybar : works quasi-perfectly with transparency.

Tested trayer but not select : problem transparency

Tested stanfolonetray but not select : problem transparency


#### Polybar

    yay -S ttf-material-design-icons 
    yay -S polybar 
    mkdir ~/.config/polybar
    cd ~/.config/polybar
    wget https://raw.githubusercontent.com/alexandrenavarro/dotfiles/master/.config/polybar/config    


See the resolution of bug for tray icon transparency https://github.com/polybar/polybar/issues/913

Tested but not selected polybar : moving window with openbox works, higly customisable, transparency but finally no need.

Tested but not selected tint2 : size for moving window with openbox does not any work with %    
    

### Bootloader (optional)

#### Grub

    sudo pacman -S grub-customizer

Use Grub Customizer to set the different settings you want, save and install to mbr.
Be sure your mbr you changed is the one launched by the motherboard (or re-set in the bios) notably if you installed another linux distribution on another disk drive.

You can also change the configuration int /etc/default/grub and update grub.

    sudo grub-mkconfig -o /boot/grub/grub.cfg
    
    
### Compositor (optional)

#### Picom
    
    sudo pacman -S picom

Needed if you want to have transparency window notably for polybar.


### Bluetooth Manager (optional)

#### Bluez
    
    sudo pacman -S bluez bluez-utils bluez-tools blueman pulseaudio-bluetooth
    yay -S bluetooth-autoconnect
    
    sudo systemctl enable bluetooth.service
    sudo systemctl enable bluetooth-autoconnect
    systemctl --user enable pulseaudio-bluetooth-autoconnect

    
See https://wiki.archlinux.org/title/bluetooth and https://github.com/jrouleau/bluetooth-autoconnect


### CPU Manager (optional)

#### Auto-cpu freq 

https://github.com/AdnanHodzic/auto-cpufreq

TODO


### Default Application Configuration

#### Add some application in the Menu of Application

   cd ~/.local/share/applications/
   
Ex :
gmail.desktop

    [Desktop Entry]
    Version=1.0
    Type=Application
    Name=Gmail
    GenericName=Gmail
    #Icon=/home/anavarro/.webcatalog/Gmail/resources/app.asar.unpacked/build/icon.png
    Exec=brave --new-window --app=https://gmail.com/
    Terminal=false
    StartupWMClass=gmail
    #Categories=Internet;
    Comment=""


#### Association files
Use a graphical File Manager like Thunar to associate your default application  or command below

##### Open a file with the default application
    
    xdg-open file.txt

##### See a filetype of a file 
    
    xdg-mime query filetype photo.jpeg

##### See the default application for a mime type
    
    xdg-mime query default image/jpeg

##### Default application for a mime type
    
    xdg-mime default feh.desktop image/jpeg

##### All default application for all mime type
    
    cat /usr/share/applications/mimeinfo.cache
    cat ~/.local/share/applications/mimeapps.list

##### All default applications
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
    
## Gaming

### Steam

    sudo pacman -S steam

Use vulkan-radeon (not amdvlk)
You can install retroarch (retrogaming) + dlc or Counter Strike - GO

### Some benchmarks

#### Glxgears

    sudo pacman -S glxgears
    vblank_mode=0 glxgears --fullscreen

#### Glmark2

    sudo pacman -S glmark2
    glmark2  --fullscreen 

#### phoronix-test-suite

    yay -S phoronix-test-suite

    # list tests
    phoronix-test-suite list-tests

    # install test
    phoronix-test-suite install pts/glmark2

    # run test
    phoronix-test-suite run pts/glmark2
    
    phoronix-test-suite install pts/unigine-valley
    phoronix-test-suite run pts/unigine-valley

    
    
    

    
