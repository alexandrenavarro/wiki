# Introduction 

Installation and configuration of the different sofware must result to :

* Every actions (or quasi) can be easily with keyboard shortcuts (compiz)
* Remove unnecessary waste of space to keep focus, only a bar potentially autohideable is accepteable, (remove title, window decoration ...) (compiz)
* The position and size of the different applications must be remembered (compiz)
* Having a global menu (like MacOsX) and accessible with keyboard shortcut, (mate-panel with mutiny + xdotool)
* Having HUD to search in menu of the application with keyboard shortcut (mate-hud)
* Easy to put windows left, right, maximize, minimize with keyboard shortcuts (compiz grid)
* Having a searcheable launcher with a keyboard shortcut (rofi --show run)
* Having a searcheable task manager with a keyboard shortcut (rofi --show window)
* Keep short as possible as the shortcuts as the one in Windows

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
    sudo apt install git fdupes pdftk    
    sudo snap install intellij-idea-community --classic --edge

### Documents
    sudo apt install libreoffice
    sudo apt install calibre
    sudo apt install pdftk
    
### Other
    sudo apt install rofi dconf-editor gnome-tweaks simple-scan
    sudo apt install openscad

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
    sdk install java 8.0.181-oracle
    sdk install kotlin
    sdk install maven
    sdk install gradle

## From bashit

    git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
    ~/.bash_it/install.sh
    
    bash-it enable plugin alias-completion dirs edit-mode-vi git gradle history hub java jenv sdkman ssh
    
    
## From AppImage
Download AppImage of Cura3D and run it

# Configuration /Installation for some applications

## Firefox

### Installation
    sudo apt install firefox

### Configuration
* Install vimium plugin
* Install fox gesture plugin
* In about:config, set to 0 the property browser.backspace_action

## Rofi

### Installation
    sudo apt install rofi

### Configuration

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
        border: 2px dash 0px 0px ;
        lines:      25;
    }

    #element selected {
        background-color: DimGray;
    }

    #element.alternate.normal {
        background-color: rgba(20, 20, 20, 100%);
    }

    #textbox-prompt-colon {
        expand:     false;
        str:        ":";
    }

    #inputbar {
        children: [prompt, textbox-prompt-colon, entry];
    }
    
## Intellij

### Configuration
Change some shorcuts
* Editor Actions | Move Caret to Code Block End : CTRL + [ (equivalent)
* Main menu | Edit | Find Usages | Find Usages : ALT + F6 (check pb with ALT + F7)
* Main menu | Navigate | Search Everywhere : CTRL + F3 (in addition of Shift / Shift)
* Main menu | Navigate | Back : Alt + Left (in addition of ALT + CTRL + Left)
* Main menu | Navigate | Forward : Alt + Right (in addition of ALT + CTRL + Right)
    
## Ranger

### Installation
    sudo apt install ranger
    
### Configuration
* Customize https://github.com/ranger/ranger/blob/master/ranger/config/rifle.conf notably for shotwell and mpv

    vi ~/.config/ranger/rifle.conf
    
### Main Menu
* Add items in System Tools
* Terminal : gnome-terminal

* Add items in System -> Administration
* Logout : mate-session-save --logout
* Restart : systemctl reboot
* Shutdown : systemctl poweroff

## Bash

### Configuration
* Add neofetch at the end of .bashrc

## LightDM (Login)
* Background : black image
* Background color : black color

## Model 01 Firmware

### Installation

Follow this https://github.com/keyboardio/Kaleidoscope/wiki/Install-Arduino-support-on-Linux and https://github.com/keyboardio/Model01-Firmware/blob/master/README.md#create-and-navigate-to-the-arduino-sketchbook-directory with the compilation by command line

## Xcape

### Installation

    sudo apt install xcape
    
### Configuration

    xcape -e 'Super_L=Super_L|r'
    
    
## Openscad

    sudo add-apt-repository ppa:openscad/releases
    sudo apt update
    sudo apt install openscad


# Configuration of Ubuntu 18.04 with mate-desktop

## Installation
    sudo apt install ubuntu-mate-desktop
    
    
## Preferred Application

### Internet
* Web Browser : Firefox
* Mail Reader : Thunderbird Mail

### Multimedia
* Image Viewer : Shotwell
* Multimedia Player : Rhythmbox Music Player
* Video Player : mpv

### System
* Text Editor : gedit
* Terminal Emulator : Terminal (Gnome-terminal)
* File Manager : Files

### Office
* Document Viewer : Document Viewer (Evince)
* Word Processor : LibreOffice Writer
* Spreadsheet Editor : LibreOffice Calc

## Appearence

### Theme 
* Use High Contrast Inverse and customize with Icons : Ubuntu-Mono-Dark

### Background
* Use an black custom image (do not use solid color, make big problem in compiz)

## MATE Tweak
### Desktop 
* Remove Show Desktop Icons

### Panel
* Set Contempary
* Enabe Hud

### Windows
* Set compiz as window manager

### Mate Global
* Remove dock on the left or right, menu on top left, set date as first element on top right.
* Add a second global menu on the right (useful when the window is on the right)

## Compiz

### Installation
    sudo apt install compizconfig-settings-manager

### General : Commands
* Super + r (and Super with xcape) (same shortcut as Windows) : rofi -combi-modi drun,run -show-icons -show combi -modi combi
* Alt + space (same shortcut as Windows with switcheroo) :  rofi -combi-modi window,drun,run -show-icons -show combi -modi combi
* Super + e (same shortcut as Windows) : nautilus
* Super + i (same shortcut as Windows) : mate-control-center
* Super + b (same shortcut as Windows) : xdotool mousemove 3426 14 click 1
* Super + Alt + Left (specific Linux) : xdotool mousemove 14 14 click 1
* Super + Alt + Right (specific Linux) : xdotool mousemove 1734 14 click 1
* Super + Ctrl + Left (specific Linux) : xdotool mousemove 860 720 click 1
* Super + Ctrl + Right (specific Linux) : xdotool mousemove 2520 720 click 1

* Super + s (same shortcut as Windows) : mate-search-tool

### Not working (problem shortcut with esc on linux)
* Ctrl + Shift + Esc (or Ctrl + Alt + Delete) (same shortcut as Windows) : /usr/bin/mate-system-monitor -p

### General : Mate Compatibilty :
* Terminal Command Line (gnome-terminal) : Super + T
* Show Main Menu (same shortcut as Windows) : Super + X

### General : General Options :
* Minimise Window (same shortcut as Windows) : Super + Down
* Show Desktop (same shortcut as Windows) : Super + d  (or Super + m)

### Desktop : Desktop Wall
* Move Left (same shortcut as Windows) : Super + Shift + Left
* Move Right (same shortcut as Windows) : Super + Shift + Right

### Effects : Animation
* Open Animation : Duration = 200
* Close Animation : Duration = 200
* Minimize Animation : Lamp Wavy
* Uninimize Animation : Lamp Wavy
* Slide with animation : Not Found :-(.

### Effects : Window Decoration
* Uncheck Window Decoration

### Windows Management : Grid
* Left Maximize (same shortcut as Windows) : Super + Left
* Right Maximize (same shortcut as Windows) : Super + Right
* Maximize Key (same shortcut as Windows) : Super + Up

### Windows Management : Place Windows 
* Add Fixed Windows Placement x=0, y=27, class=Gnome-terminal | class=Nautilus | class=class=Mate-system-monitor
* Add Fixed Windows Placement x=1720, y=27, class=Ccsm | class=Firefox| class=Shotwell | class=Rhythmbox | class=mpv | class=Gedit | class=Evince | class=libreoffice-writer | class=libreoffice-calc | class=Mate-control-center | class=Dconf-editor 

### Windows Management : Window Rules
* Add Size Rules,  width=1720, height=1413, class=Ccsm | class=mpv | class=Rhythmbox | class=Gedit | class=Gnome-terminal | class=Nautilus | class=Mate-system-monitor | class=Dconf-editor

### Windows Management : Shift Switcher
* Activate it (same shortcut as Windows)

## Jayatana
*  Having Swing menu in the global menu (does not work)

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


# Configuration of non-detected hardware

## Epson EcoTank ET-4750
Search ET-4700 http://download.ebz.epson.net/dsc/search/01/search/searchModuleFromResult

### Printer
It works but you can have more option

http://download.ebz.epson.net/dsc/search/01/search/searchModuleFromResult

Install Driver + Utility
Add a printer through find Network printer.

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
    gedit /etc/imagescan/imagescan.conf

with

    [devices]
    net.udi = networkscan:esci://192.168.0.6:1865
    net.vendor = Epson 
    net.model = Epson EcoTank ET-4750
    net.name = Epson EcoTank ET-4750

Launch 

### Printer
// TODO automatically discovered but doesn't launch everytime a print



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



# Distribution ugrade

## From non-LTS

    sudo apt update 
    sudo apt upgrade
    sudo apt dist-upgrade

## From LTS to non-LTS

    # change Prompt=LTS to Prompt=normal
    vi /etc/update-manager/release-upgrades 
    
    sudo do-release-upgrade -d
