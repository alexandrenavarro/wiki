# Introduction 

Installation and configuration of the different sofware must result to :

* Every actions (or quasi) can be easily with keyboard shortcuts.
* Remove unnecessary waste of space to keep focus, only a bar potentially autohideable is accepteable, (remove title, window decoration ...), (compiz window decoration)
* The position and size of the different applications must be remembered (devilspie if l)
* Having a global menu (like MacOsX) and accessible with keyboard shortcut, (mate-panel with mutiny / vala-app-menu + xdotool)
* Having HUD to search in menu of the application with keyboard shortcut (mate-hud)
* Easy to put windows left, right, maximize, minimize with keyboard shortcuts (compiz grid)
* Having a searcheable launcher with a keyboard shortcut (rofi --show run)
* Having a searcheable task manager with a keyboard shortcut (rofi --show window)
* Keep short as possible as the shortcuts as the one in Windows

# Software Installation

## From apt / snap
    sudo apt update

### Network
    sudo apt install curl chromium-browser transmission
    
### Mutimedia  
    sudo apt install ubuntu-restricted-extras vlc mplayer handbrake sound-juicer brasero
    sudo apt install digikam 
    
### Utilities    
    sudo apt install ranger fdupes baobab git htop neofetch
    
    sudo snap install intellij-idea-community --classic --edge

### Documents
    sudo apt install libreoffice-writer
    sudo apt install calibre
    
### Other
    sudo apt install rofi dconf-editor gnome-tweaks devilspie2 chrome-gnome-shell simple-scan
    sudo apt install lighdm openscad compizconfig-settings-manager

## From custom apt repository

### Hub
    sudo add-apt-repository ppa:cpick/hub
    sudo apt update
    sudo apt install hub

### Last Git
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt update
    sudo apt install git

## From sdkman

    curl -s "https://get.sdkman.io" | bash 
    source "$HOME/.sdkman/bin/sdkman-init.sh"
    sdk install java
    sdk install kotlin
    sdk install maven
    sdk install gradle
    sdk install kscript

## From bashit

    git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
    ~/.bash_it/install.sh
    
    bash-it enable plugin alias-completion dirs edit-mode-vi git gradle history hub java jenv sdkman ssh
    
    

## From AppImage
Download AppImage of Cura3D and run it


# Configuration of Ubuntu 18.04 with mate-desktop

## Installation
    sudo apt install ubuntu-mate-desktop

## Appearence

### Theme 
* Use High Contrast Inverse and customize with Icons : Ubuntu-Mono-Dark

### Background
* Use an black custom image (do not use solid color, make big problem in compiz)

## MATE Tweak
### Desktop 
* Remove Show Desktop Icons

### Panel
* Set Mutiny
* Enabe Hud

### Windows
* Set compiz as window manager

### Mate Global
* Remove dock and Add Brisk Menu on Top Left
* Remove dock on the left
* Add a second global menu on the right (usefull when the window is on the right)

## LightDM (Login)
* Background : black image
* Background color : black color

## Compiz

### Installation
    sudo apt install compizconfig-settings-manager

### Effects : Window Decoration
* Uncheck Window Decoration

### Windows Management : Grid
* Put Left Key : Super + Left
* Put Right Key : Super + Right
* Maximize Key : Super + Up

### Commands
* Super + r : rofi -combi-modi window,run -show combi -modi combi
* Super + esc : rofi -show window
* Super + Space (to redifine, maybe Super + Ctrl + left and Super + Home) : xdotool mousemove 14 14 click
* Super + Shift + Space (to redifine, maybe Super + Ctrl + left and Super + End) : xdotool mousemove 1734 14 click 


### General Options :
* Close Window : Super + q
* Minimise Window : Super + Down

#### Windows logo key keyboard shortcuts

* Windows logo key  	                Open or close Start (TODO)
* Windows logo key  + B 	            Set focus in the notification area (TODO)
* Windows logo key  + Shift + C         Open the charms menu (Check is it?)
* Windows logo key  + D 	            Display and hide the desktop (TODO?)
* Windows logo key  + Alt + D 	        Display and hide the date and time on the desktop (TODO?)
* Windows logo key  + E 	            Open File Explorer (TODO)
* Windows logo key  + F 	            Open Feedback Hub and take a screenshot (Check what is?)
* Windows logo key  + G 	            Open Game bar when a game is open (Not Useful)
* Windows logo key  + H 	            Start dictation (Not Useful)
* Windows logo key  + I 	            Open Settings (TODO)
* Windows logo key  + J                 Set focus to a Windows tip when one is available. (Not Useful)
* Windows logo key  + K 	            Open the Connect quick action (Check what is it)
* Windows logo key  + L 	            Lock your PC or switch accounts (TODO)
* Windows logo key  + M 	            Minimize all windows (TODO
* Windows logo key  + O 	            Lock device orientation (Not Useful)
* Windows logo key  + P 	            Choose a presentation display mode (Not Useful)
* Windows logo key  + R 	            Open the Run dialog box (TODO)
* Windows logo key  + S 	            Open search (Check what is)
* Windows logo key  + T 	            Cycle through apps on the taskbar (Check what is)
* Windows logo key  + U 	            Open Ease of Access Center (Check what is)
* Windows logo key  + V 	            Cycle through notifications (Check what is)
* Windows logo key  + Shift + V         Cycle through notifications in reverse order (Check what is)
* Windows logo key  + X 	            Open the Quick Link menu (Check what is)
* Windows logo key  + Y 	            Switch input between Windows Mixed Reality and your desktop (Check what is)
* Windows logo key  + Z 	            Show the commands available in an app in full-screen mode (Check what is)
* Windows logo key  + period (.) or semicolon (;)   Open emoji panel (Not Useful)
* Windows logo key  + comma (,)         Temporarily peek at the desktop (Check what is)
* Windows logo key  + Pause 	        Display the System Properties dialog box (TODO?)
* Windows logo key  + Ctrl + F 	        Search for PCs (if you're on a network) (Check what is)
* Windows logo key  + Shift + M         Restore minimized windows on the desktop (TODO?)
* Windows logo key  + number 	        Open the desktop and start the app pinned to the taskbar in the position indicated by the number. If the app is already running, switch to that app. (No Sense)
* Windows logo key  + Shift + nbr       Open the desktop and start a new instance of the app pinned to the taskbar in the position indicated by the number (No Sense)
* Windows logo key  + Ctrl + nbr        Open the desktop and switch to the last active window of the app pinned to the taskbar in the position indicated by the number (No Sense)
* Windows logo key  + Alt + nbr         Open the desktop and open the Jump List for the app pinned to the taskbar in the position indicated by the number (No Sense)
* Windows logo key  + Ctrl + Shift + nbr    Open the desktop and open a new instance of the app located at the given position on the taskbar as an administrator (No Sense)
* Windows logo key  + Tab               Open Task view (TODO)
* Windows logo key  + Up arrow          Maximize the window (DONE)
* Windows logo key  + Down arrow        Remove current app from screen or minimize the desktop window (DONE)
* Windows logo key  + Left arrow        Maximize the app or desktop window to the left side of the screen (DONE)
* Windows logo key  + Right arrow       Maximize the app or desktop window to the right side of the screen (DONE)
* Windows logo key  + Home 	            Minimize all except the active desktop window (restores all windows on second stroke) (TODO)
* Windows logo key  + Shift + Up arrow 	Stretch the desktop window to the top and bottom of the screen (TODO?)
* Windows logo key  + Shift + Down arrow    Restore/minimize active desktop windows vertically, maintaining width (TODO?)
* Windows logo key  + Shift + Left arrow or Right arrow 	Move an app or window in the desktop from one monitor to another (TODO?)
* Windows logo key  + Spacebar          Switch input language and keyboard layout (TODO?)
* Windows logo key  + Ctrl + Spacebar   Change to a previously selected input (TODO?)
* Windows logo key  + Ctrl + Enter      Open Narrator (Check what is it)
* Windows logo key  + Plus (+)          Open Magnifier (Check what is it)
* Windows logo key  + forward slash (/) Begin IME reconversion (Check what is it)
* Windows logo key  + Ctrl + V          Open shoulder taps (Check what is it)

#### Copier, coller et autres raccourcis clavier généraux
* Ouvrir le menu Démarrer : Ctrl + Échap
* Gestionnaire des tâches : Ctrl + Maj + Échap

#### Raccourcis clavier de bureaux virtuels
* Touche de logo Windows  + Tabulation 	Ouvrir les Applications actives
* Touche de logo Windows  + Ctrl + D 	Ajouter un bureau virtuel
* Touche de logo Windows  + Ctrl + Flèche droite 	Basculer entre les bureaux virtuels que vous avez créés sur la droite
* Touche de logo Windows  + Ctrl + Flèche gauche 	Basculer entre les bureaux virtuels que vous avez créés sur la gauche
* Touche de logo Windows  + Ctrl + F4 	Fermer le bureau virtuel que vous utilisez

### Effects : Animation
* *TODO* 
** slide left right
** lamp when minimize / back


## Firefox
* Install vimium plugin
* Install fox gesture plugin

## Rofi

### Installation
    sudo apt install rofi

### Configuration Theme
    vi ~/.config/rofi/config.rasi


      * {
        background-color: Black;
        border-color:     GhostWhite;
        text-color:       GhostWhite;
    }

    #window {
        border: 1;
        padding: 4;
    }


    #listview {
        lines:      25;
    }

    #element selected {
        background-color: DimGray;
    }

    #element.alternate.normal {
        background-color: rgba ( 20, 20, 20, 100 % );
    }  
    
### Configuration for shutdown / reboot

* *TODO* custom menu for shutdow / reboot / logout


## Jayatana
*  Having Swing menu in the global menu (does not work)
    sudo apt install jayatana



# Configuration of Ubuntu 18.04 with gnome-shell (Alternative of mate)

## Gnome Shell Tweak

### Appearance
* Applications : Adwaita-dark

### Desktop 
Show Icons : off

### Top Bar
Application Menu : off


### Extentions

    sudo apt install chrome-gnome-shell

#### Unite (undecorated windows)
* Hide activities button : Always
* Hide windows titlebars : Both
* Show window title in app menu : Always
* Show window buttons int top bar : Never

#### Dash to dock (remove dock on the left)
*   and Size : Intelligent autohide -> Dodge windows : off

#### Gnome global application menu(hud for gnome) : (global menu / HUD)
* !!! Caution !!! Not very stable (close all windows randomly) but great in term of features.

#### Swither (manage search windows)

## Devilspie2 (Windows Placement / Size, maybe use a Gnome Shell Extensions if exists)

### Installation
    sudo apt install devilspie2

### Configuration
//TODO Complete with all apps

    cd 
    mkdir .config/devilspie2
    cd .config/devilspie2  
    
    vi devilspie2.lua

    if (get_application_name() == "Terminal") then
      set_window_geometry(0, 27, 1720, 1413);
      undecorate_window();
    end
    if (get_application_name() == "Firefox" or
        get_application_name() == "Nautilus" or
        get_application_name() == "Caja") then
      set_window_geometry(1720, 27, 1720, 1413);
      undecorate_window();
    end





