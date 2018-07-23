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

## From custum apt / snap

### Intellij
//TODO

### Hub
//TODO

### Last Git
// TODO

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

## MATE Tweak
### Desktop 
* Remove Show Desktop Icons

### Panel
* Set Mutiny
* Enabe Hud

### Windows
* Remove dock
* Add launcher on top left
* Set compiz as window manager

## Mate Global
* Add Brisk Menu on Top Left
* Remove dock on the left

## Background
* *TODO Set Black background (do not use solid color, make big problem in compiz)

## Brisk Menu
* *TODO Set Black background

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
* Super + Space (to redifine) : xdotool mousemove 64 12 click 
* Super + r : rofi -combi-modi window,run -show combi -modi combi
* Super + esc : rofi -show window

### General Options :
* Close Window : Super + q
* Minimise Window : Super + Down

* *TODO all Windows super  must be mapped*

#### Raccourcis clavier de la touche de logo Windows
* Mettre le focus dans la zone de notification : Super + b
* Afficher et masquer le bureau : Super + d (useful?)
* Afficher et masquer la date et l’heure sur le bureau :  Super + Alt + D (useful?)
* Ouvrir l'Explorateur de fichiers : Super + E
* Ouvrir les Paramètres : Super + I
* Verrouiller le PC ou changer de compte : Super + l
* Réduire toutes les fenêtres : Super + m 
* Parcourir les notifications : Super + V (useful?)
* Parcourir les notifications dans l’ordre inverse : Super + Maj + V (useful?)
* Ouvrir le menu Lien rapide : Super + X 
* Afficher la boîte de dialogue Propriétés système : Super + Pause (useful?)
* Restaurer les fenêtres réduites sur le bureau : Super + Maj + M (useful?)
* Réduire tout à l’exception de la fenêtre active du bureau (restaure toutes les fenêtres à la deuxième frappe de touche): Super + Home

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


## Devilspie

### Installation
    sudo apt install devilspie2

### Configuration
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

## Dark theme

* Set the theme in appareance adwaita-dark
// * TODO

## Firefox
* Install vimium plugin
* Install fox gesture plugin

## Rofi

### Installation
    sudo apt install rofi

### Configuration

* *TODO* custom menu for shutdow / reboot / logout
* *TODO* custom theme

## Jayatana
*  Having Swing menu in the global menu (does not work)
    sudo apt install jayatana



# Configuration of Ubuntu 18.04 with gnome-shell

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
* Not very stable (close all windows randomly) but great in term of features.

#### Swither (manage search windows)




