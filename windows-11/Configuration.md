# Software Installation

### Accessories

#### File Editor (on the right zone)
    notepad++

#### Archive Manager (on right zone)
    7zip
    
#### Disk Usage (on the right zone)
    spacemonger
    
#### Pdf Document Viewer (on the right zone)
    sumatrapdf
    
### Graphics  

#### Image Viewer (on the right zone)
    TODO
    
### Internet 

#### Web Browser (on the right zone)
    Brave

### Office (on the right zone)
    libreoffice

### Sound & Video
#### Video Player (full screen)
    vlc

#### Music Player (on the right zone)
    TODO

#### DVD Ripper (on the right zone)
    handbrake (copy and encode dvd)
    makekv (used just for copy dvd to hard disk when some other can't suceed it)

#### DVD Burner(on the right zone)
    TODO
    
### Utilities   
    git

### System Tools

#### Window Manager
    PowerToys - FancyZones
    
Configuration
* Enable Fancy Zones
* Editor
Launch Layout Editor
  - Set 2 colums in Columns for screen >= 27 pouces
  - Set 1 colums in Grid for screen <27 pouces (but with 2 screens)
* Windows
  - Move newly created
* Override Window Snap
  - Move window based on Zone Win + < - >
  - Move window between zones across all screens

#### Launcher / Window Switcher
    PowerToys - Run (seems to be Flow Launcher)

Configuration
* Activate Windows Waller with a score of 1000 to have current windows on the top

#### File Explorer (on the left zone)
    explorer++

#### Terminal (on the left zone)
    gitbash

#### Monitor
    No needed

#### Disks
    TODO

#### Intellij (fullscreen)
Add in your VMoption if you want to have a real title bar
-Dide.win.frame.decoration=false


##### AutoHotKey (Deprecated since you use Power Toys Fancy Zone

Create a script.ahk for tiling windows with some shortcuts

    #NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
    ; #Warn  ; Enable warnings to assist with detecting common errors.
    SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
    SetWorkingDir %A_ScriptDir%  ; Ensures a consistent starting directory.
    
    #+Left::WinMove,A,,0,30,A_ScreenWidth/2,(A_ScreenHeight-30)
    #+Down::WinMinimize,A
    #+Up::WinMove,A,,0,30,A_ScreenWidth,(A_ScreenHeight-30)
    #+Right::WinMove,A,,A_ScreenWidth/2,30,A_ScreenWidth/2,(A_ScreenHeight-30)
