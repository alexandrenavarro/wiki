# Connect via ssh

     ssh pi@192.168.0.2

# Clock update 

    sudo service ntp stop
    sudo ntpd -gq
    sudo service ntp start
    
    
# Fix Bluetooth
    # Launch bluetooth controller
    bluetoothctl
    # Scan it
    scan on
    # if No default controller available, launch before
    sudo systemctl start hciuart
