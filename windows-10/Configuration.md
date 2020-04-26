# Software Installation

## AutoHotKey

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


