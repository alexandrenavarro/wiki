# Keyboardio Model 01

## My personal layout 

https://github.com/alexandrenavarro/Model01-Firmware/blob/master/README-WHY-MY-PERSONAL-LAYOUT.md

## Why I did this layout?

### Wanted
* Super access to shortcuts to navigate in a file and on homerow on left, right, up and down (it will be on the right fn).
* Super access shortcuts for most used like the on generally in File or Edit meun with on homerow (it will be on the left fn, first row for file, homerow for delete, undo, cut, copy, paste, find, go to, must be on left to use it with the hand of the mouse)
* Super easy access to search in windows (like switchero on windows and rofi on linux), app (like executor.dk on window and rofi on linux) and also in app tabs (it will be on palm key)
* Easy access to numpad (it will be on the right num on first and homerow)
* Easy access to Super + direction (it will be on the right num on third row)
* Easy access to altgr for bépo (it will be on the left num) with some adaption from altgr of bépo
* Super acces to shortcuts to navigate in different file through Intellij (third row on the left fn)
* Alt tab, Esc must be on the left to use it with the hand on the mouse
* Shift management must be as quick as possible (OneShot plugin is used)
* All modifier can be easily useable (OneShot plugin is used for Alt/Ctrl)
* Vi mode should be great for composed command.

### Plugins used
* Macros to do some simulate mainly shortcuts.
* OneShot on all modifiers to simplify the use of modifier.
* Qukeys to have different behiavior for one key.
* ActiveModColorEffect to see which modifier is set.
* Leader to simulate a kind of vi mode.

### Installation

Follow this https://kaleidoscope.readthedocs.io/en/latest/setup_toolchain.html#Arduino-Linux

Caution, install by the hand arduino IDE (on Ubuntu because old version but also on arch because path is not the same).

    cd ~/Downloads
    tar xvf arduino-1.8.13-linux64.tar.xz
    sudo mv arduino-1.8.13 /usr/local/arduino
    cd /usr/local/arduino
    sudo ./install.sh
    
By default, you may not have permissions to access your keyboard’s serial port so need to activate it.
    
    wget https://raw.githubusercontent.com/keyboardio/Kaleidoscope/master/etc/60-kaleidoscope.rules
    sudo cp 60-kaleidoscope.rules /etc/udev/rules.d

On Debian / Ubuntu distrib
    
    sudo /etc/init.d/udev reload

On arch distrib (caution need the sudo contrary to the documentation)
    
    sudo udevadm control --reload-rules && udevadm trigger
    
       

Some others information are available on https://github.com/keyboardio/Model01-Firmware/blob/master/README.md#create-and-navigate-to-the-arduino-sketchbook-directory with the compilation by command line.


## My arduino repository with this layout
https://github.com/alexandrenavarro/Model01-Firmware


## Compile it.

    make
    
## Compile and flash it.

    make flash

