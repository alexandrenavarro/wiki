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

# Installation Software

## From apt
    sudo apt update

    sudo apt install \
    rofi \
    mate-desktop \
    chromium-browser \
    git \
    ubuntu-restricted-extras \
    vlc \
    dconf-editor \
    openjdk-8-jre openjdk-8-jdk \
    compizconfig-settings-manager \
    curl \
    blackbird-gtk-theme

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
    
    bash-it enable plugin gradle

* *TODO* add different plugins


# Configuration of Ubuntu 18.04 with mate-desktop

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
* Restore : Super + Down
* Put Top Left Key : Super + PgDown
* Put Top Up Key : Super + PgUp
* Put Bottom Left Key : Super + Ctrl + PgDown
* Put Bottom Up Key : Super + Ctrl + PgUp

### Commands

* Super + Esc : rofi -show combi
* Super + Space : xdotool mousemove 64 12 click 1
* Super + q : equivalent of F1
* Super + r : rofi -show run
* *TODO all Windows super must be mapped*

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
* *TODO* Working Java menu (sudo apt install jayatana)





