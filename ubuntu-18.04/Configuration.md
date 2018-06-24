# Installation Software

## From Distribution
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

## From Sdkman

    curl -s "https://get.sdkman.io" | bash 
    source "$HOME/.sdkman/bin/sdkman-init.sh"
    sdk install java
    sdk install kotlin
    sdk install maven
    sdk install gradle
    sdk install kscript

## From Bashit

TODO

# Configuration
## Firefox
Install vimium / firegesture

## MATE Tweak
### Desktop 
Remove Show Desktop Icons

### Panel
Enabe Hud

### Windows
Mutiny, remove dock, add launcher top left, set compiz

## Mate Global
Remove dock on the left

## Compiz

### Effects : Window Decoration
Uncheck Window Decoration

### Windows Management : Grid
Set Super + arrow

### Commands
Super + Space : rofi -mode combi
Super + H : xdotool mousemove 64 12 click 1

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
Set the theme in appareance (blackbird-gtk-theme)

# TODO
* All keyboard Windows mapped.
* Working Java menu (sudo apt install jayatana)






