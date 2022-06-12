# Software Installation

### Accessories

#### File Editor
    micro
    notepad
Adopted : micro (memory 30mo, have terminal mode, classical keyshortcuts)
Adopted in second choice : notepad++

#### Archive Manager
    7zip
    
#### Disk Usage
    spacemonger
    
#### Pdf Document Viewer
    acrobatreader
    
### Graphics  

#### Image Viewer
    TODO
    
### Internet

#### Web Browser
    Brave

### Office
    libreoffice

### Sound & Video
#### Video Player
    vlc

#### Music Player
    TODO

#### DVD Ripper
    handbrake (copy and encode dvd)
    makekv (used just for copy dvd to hard disk when some other can't suceed it)

#### DVD Burner
    TODO
    
### Utilities   
    git

### System Tools

#### File Explorer
    File Explorer
    lf

Adopted : lf (terminal)

#### Terminal
    alacritty

TODO config for gitbash

#### Launcher / Window Switcher
    Flow + Window Walker plugin - https://github.com/taooceros/Flow.Plugin.WindowWalker
    pm install window walker

Increase the priority to 1 to have windows first before launching a new instance of the application.

#### Monitor
    TODO

#### Disks
    TODO
    
#### Window Manager Emulation    
        
##### AutoHotKey

Create a script.ahk for tiling windows with some shortcuts

    #NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
    ; #Warn  ; Enable warnings to assist with detecting common errors.
    SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
    SetWorkingDir %A_ScriptDir%  ; Ensures a consistent starting directory.
    
    #+Left::WinMove,A,,0,30,A_ScreenWidth/2,(A_ScreenHeight-30)
    #+Down::WinMinimize,A
    #+Up::WinMove,A,,0,30,A_ScreenWidth,(A_ScreenHeight-30)
    #+Right::WinMove,A,,A_ScreenWidth/2,30,A_ScreenWidth/2,(A_ScreenHeight-30)

##### Window Manager
TODO Find a way to save position of the different application or something closed.

#### Intellij
Add in your VMoption if you want to have a real title bar
-Dide.win.frame.decoration=false
