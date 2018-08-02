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
    sudo apt install curl chromium-browser transmission
    
### Mutimedia  
    sudo apt install ubuntu-restricted-extras mpv handbrake sound-juicer brasero
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

# Configuration for some applications

## Firefox

### Installation
    sudo apt install firefox

### Configuration
* Install vimium plugin
* Install fox gesture plugin

## Rofi

### Installation
    sudo apt install rofi

### Configuration
* *TODO* launch when super is released.


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
    
## Ranger

### Installation
    sudo apt install ranger
    
### Configuration
* Customize https://github.com/ranger/ranger/blob/master/ranger/config/rifle.conf notbly for shotwell and mpv

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
* Set Mutiny
* Enabe Hud

### Windows
* Set compiz as window manager

### Mate Global
* Remove dock on the left
* Add a second global menu on the right (useful when the window is on the right)

## Compiz

### Installation
    sudo apt install compizconfig-settings-manager

### General : Commands
* Super + r : rofi -combi-modi window,drun,run -show-icons -show combi -modi combi
* Super + esc : rofi -show window
* Super + Space (to redifine, maybe Super + Ctrl + left and Super + Home) : xdotool mousemove 64 14 click
* Super + Shift + Space (to redifine, maybe Super + Ctrl + left and Super + End) : xdotool mousemove 1734 14 click 

### General : General Options :
* Close Window : Super + q
* Minimise Window : Super + Down

### Effects : Animation
* Open Animation : Duration = 200
* Close Animation : Duration = 200
* Minimize Animation : Lamp Wavy
* Uninimize Animation : Lamp Wavy
* TODO Slide with animation

### Effects : Window Decoration
* Uncheck Window Decoration

### Windows Management : Grid
* Put Left Key : Super + Left
* Put Right Key : Super + Right
* Maximize Key : Super + Up

### Windows Management : Place Windows 
* Add Fixed Windows Placement x=0, y=27, class=Gnome-terminal | class=Nautilus | class=class=Mate-system-monitor
* Add Fixed Windows Placement x=1720, y=27, class=Ccsm | class=Firefox| class=Shotwell | class=Rhythmbox | class=mpv | class=Gedit | class=Evince | class=libreoffice-writer | class=libreoffice-calc | class=Mate-control-center | class=Dconf-editor 

### Windows Management : Window Rules
* Add Size Rules,  width=1720, height=1413, class=Ccsm | class=mpv | class=Rhythmbox | class=Gedit | class=Gnome-terminal | class=Nautilus | class=Mate-system-monitor | class=Dconf-editor

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


# Configuration to do to have the same shortcuts as Windows

## TODO shortcuts

#### Copy, paste, and other general keyboard shortcuts
* Windows logo key  + D 	            Display and hide the desktop (TODO)
* Ctrl + Esc                            Open Start (TODO)
* Ctrl + Shift + Esc                    Open Task Manager (TODO)

#### Windows logo key keyboard shortcuts
* Windows logo key  	                Open or close Start (TODO)
* Windows logo key  + B 	            Set focus in the notification area (TODO)
* Windows logo key  + E 	            Open File Explorer (TODO)
* Windows logo key  + I 	            Open Settings (TODO)
* Windows logo key  + M 	            Minimize all windows (TODO)
* Windows logo key  + S 	            Open search (TODO)
* Windows logo key  + Tab               Open Task view (TODO)
* Windows logo key  + Home 	            Minimize all except the active desktop window (restores all windows on second stroke) (TODO)
* Windows logo key  + Shift + Up arrow 	Stretch the desktop window to the top and bottom of the screen (TODO?)
* Windows logo key  + Shift + Down arrow    Restore/minimize active desktop windows vertically, maintaining width (TODO?)

#### Windows logo key keyboard shortcuts

* Windows logo key  + Tab                 Open Task view (TODO)
* Windows logo key  + Ctrl + D            Add a virtual desktop (TODO)
* Windows logo key  + Ctrl + Right arrow  Switch between virtual desktops you’ve created on the right (TODO)
* Windows logo key  + Ctrl + Left arrow   Switch between virtual desktops you’ve created on the left (TODO)
* Windows logo key  + Ctrl + F4           Close the virtual desktop you're using (TODO)


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
* Windows logo key  + D 	    Display and hide the desktop (TODO)
* F2                            Rename the selected item (DONE by default)
* F3                            Search for a file or folder in File Explorer (Ctrl + F In Nautilus)
* F4                            Display the address bar list in File Explorer (Ctrl + L In Nautilus)
* F5                            Refresh the active window (DONE by default)
* F6                            Cycle through screen elements in a window or on the desktop (DONE by default)
* F10                           Activate the Menu bar in the active app (DONE on some app)
* Alt + F8                      Show your password on the sign-in screen (No, Rezize window)
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
* Ctrl + arrow key  + Spacebar 	Select multiple individual items in a window or on the desktop (TODO?)
* Ctrl + Shift with an arrow keySelect a block of text (DONE by default)
* Ctrl + Esc                    Open Start (TODO)
* Ctrl + Shift + Esc            Open Task Manager (TODO)
* Ctrl + Shift                  Switch the keyboard layout when multiple keyboard layouts are available (No need)
* Ctrl + Spacebar               Turn the Chinese input method editor (IME) on or off (No need)
* Shift + F10                   Display the shortcut menu for the selected item (DONE by default)
* Shift with any arrow key      Select more than one item in a window or on the desktop, or select text in a document (DONE by default)
* Shift + Delete                Delete the selected item without moving it to the Recycle Bin first (No need)
* Right arrow                   Open the next menu to the right, or open a submenu (DONE by default)
* Left arrow                    Open the next menu to the left, or close a submenu (DONE by default)
* Esc                           Stop or leave the current task (DONE by default)

#### Windows logo key keyboard shortcuts

* Windows logo key  	                Open or close Start (TODO)
* Windows logo key  + B 	            Set focus in the notification area (TODO)
* Windows logo key  + Shift + C         Open the charms menu (Do nothing visible)
* Windows logo key  + D 	            Display and hide the desktop (TODO)
* Windows logo key  + Alt + D 	        Display and hide the date and time on the desktop (Not Useful)
* Windows logo key  + E 	            Open File Explorer (TODO)
* Windows logo key  + F 	            Open Feedback Hub and take a screenshot (Not Useful)
* Windows logo key  + G 	            Open Game bar when a game is open (Not Useful)
* Windows logo key  + H 	            Start dictation (Not Useful)
* Windows logo key  + I 	            Open Settings (TODO)
* Windows logo key  + J                 Set focus to a Windows tip when one is available. (Not Useful)
* Windows logo key  + K 	            Open the Connect quick action (Not Useful)
* Windows logo key  + L 	            Lock your PC or switch accounts (DONE by default)
* Windows logo key  + M 	            Minimize all windows (TODO)
* Windows logo key  + O 	            Lock device orientation (Not Useful)
* Windows logo key  + P 	            Choose a presentation display mode (Not Useful)
* Windows logo key  + R 	            Open the Run dialog box (DONE)
* Windows logo key  + S 	            Open search (TODO)
* Windows logo key  + T 	            Cycle through apps on the taskbar (Check what is)
* Windows logo key  + U 	            Open Ease of Access Center (Check what is)
* Windows logo key  + V 	            Cycle through notifications (Check what is)
* Windows logo key  + Shift + V         Cycle through notifications in reverse order (Check what is)
* Windows logo key  + X 	            Open the Quick Link menu (Check what is)
* Windows logo key  + Y 	            Switch input between Windows Mixed Reality and your desktop (Check what is)
* Windows logo key  + Z 	            Show the commands available in an app in full-screen mode (Check what is)
* Windows logo key  + period (.) or semicolon (;)   Open emoji panel (Not Useful)
* Windows logo key  + comma (,)         Temporarily peek at the desktop (Check what is)
* Windows logo key  + Pause 	        Display the System Properties dialog box (Not Useful)
* Windows logo key  + Ctrl + F 	        Search for PCs (if you're on a network) (Check what is)
* Windows logo key  + Shift + M         Restore minimized windows on the desktop (Not Useful)
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
* Windows logo key  + Shift + Left arrow or Right arrow 	Move an app or window in the desktop from one monitor to another (Not Useful)
* Windows logo key  + Spacebar          Switch input language and keyboard layout (Not Useful)
* Windows logo key  + Ctrl + Spacebar   Change to a previously selected input (Not Useful)
* Windows logo key  + Ctrl + Enter      Open Narrator (Check what is it)
* Windows logo key  + Plus (+)          Open Magnifier (Check what is it)
* Windows logo key  + forward slash (/) Begin IME reconversion (Check what is it)
* Windows logo key  + Ctrl + V          Open shoulder taps (Check what is it)

#### Virtual desktops keyboard shortcuts
* Windows logo key  + Tab                 Open Task view (TODO)
* Windows logo key  + Ctrl + D            Add a virtual desktop (TODO)
* Windows logo key  + Ctrl + Right arrow  Switch between virtual desktops you’ve created on the right (TODO)
* Windows logo key  + Ctrl + Left arrow   Switch between virtual desktops you’ve created on the left (TODO)
* Windows logo key  + Ctrl + F4           Close the virtual desktop you're using (TODO)



