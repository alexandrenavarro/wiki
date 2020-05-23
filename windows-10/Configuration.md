# Software Installation

### Accessories
#### File Editor
    micro
    nto
Adopted : micro (memory 30mo, have terminal mode, classical keyshortcuts)
Adopted in second choice : notepad++

#### Archive Manager
    7zip
    
#### Disk Usage
    TODO
    
#### Pdf Document Viewer
    TODO
    
### Graphics  

#### Image Viewer
    TODO
    
### Internet

#### Web Browser
     Firefox

### Office
    libreoffice

### Sound & Video
#### Video Player
    Vlc

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
    lf


Adopted : lf (terminal)

#### Terminal
    TODO

#### Launcher
    Executor

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
    
    #^Home::WinMove,A,,0,0,A_ScreenWidth/2,A_ScreenHeight/2
    #^+Up::WinMove,A,,0,0,A_ScreenWidth,A_ScreenHeight/2
    #^PgUp::WinMove,A,,A_ScreenWidth/2,0,A_ScreenWidth/2,A_ScreenHeight/2
    #^End::WinMove,A,,0,A_ScreenHeight/2,A_ScreenWidth/2,A_ScreenHeight/2
    #^+Down::WinMove,A,,0,A_ScreenHeight/2,A_ScreenWidth,A_ScreenHeight/2
    #^PgDn::WinMove,A,,A_ScreenWidth/2,A_ScreenHeight/2,A_ScreenWidth/2,A_ScreenHeight/2

    #^Left::WinMove,A,,0,0,A_ScreenWidth/2,A_ScreenHeight
    #^Down::WinMinimize,A
    #^Up::WinMove,A,,0,0,A_ScreenWidth,A_ScreenHeight
    #^Right::WinMove,A,,A_ScreenWidth/2,0,A_ScreenWidth/2,A_ScreenHeight

 
#### Intellij
Add in your VMoption if you want to have a real title bar
-Dide.win.frame.decoration=false
