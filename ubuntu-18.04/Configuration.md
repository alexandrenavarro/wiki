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
    sudo apt install shotwell digikam 
    
### Utilities    
    sudo apt install ranger fdupes baobab git htop neofetch
    
    sudo snap install [intellij-idea-community] --classic --edge

### Documents
    sudo apt install calibre
    
### Other
    sudo apt install rofi dconf-editor
    sudo apt install lighdm openscad compizconfig-settings-manager

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

## Gnome Shell Tweak
### Extentions
* Dash to dock (remove dock on the left)
* Gnome global application menu(hud for gnome) : (global menu / HUD)
* Swither (manage search windows)
* Unite (undecorated windows)


## MATE Tweak
### Desktop 
* Remove Show Desktop Icons

### Panel
* Enabe Hud

### Windows
* Set Mutiny
* Remove dock
* Add launcher on top left
* Set compiz as window manager

## Mate Global
* Remove dock on the left



## Compiz

### Effects : Window Decoration
* Uncheck Window Decoration

### Windows Management : Grid

* Put Left Key : Super + Left
* Put Right Key : Super + Right
* Maximise Key : Super + Up
* Put Top Left Key : Super + PgDown
* Put Top Up Key : Super + PgUp
* Put Bottom Left Key : Super + Ctrl + PgDown
* Put Bottom Up Key : Super + Ctrl + PgUp


### Commands

* Super + Esc : rofi -show combi
* Super + Space : xdotool mousemove 64 12 click 1
* Super + q : equivalent of F1
* Super + r : rofi -show run

### General Options :
* Close Window : Super + q
* Minimise Window : Super + Down

* *TODO all Windows super must be mapped*

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

## Devilspie
vi ~.devilpsie/devilspie.ds

    (begin
    
      (if
        (is (application_name) "Terminal")
        (geometry "1720x1412+0+28")
      )
  
      (if
       (or
         (is (application_name) "Firefox")
         (is (application_name) "nautilus")
         (is (application_name) "Caja")
       )
       (geometry "1720x1412+1720+28")
      )
  
    )

## Dark theme
    sudo apt install blackbird-gtk-theme 

* Set the theme in appareance (blackbird-gtk-theme or adwaita-dark)

## Firefox
* Install vimium plugin
* Install firegesture plugin

## Rofi
* *TODO* custom menu for shutdow / reboot / logout

## Jayatana
*  Having Swing menu in the global menu (does not work)
    sudo apt install jayatana





