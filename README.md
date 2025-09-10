# archSetup
Playing around with arch linux system.

TO DO:
1 - Learn to use Vim and customize it. 
2 - Essentials: Image Viewer, Audio Player, Video Player, Alternatives to Word, Excel, Point.
3 - Install: FreeCad, Godot 4, Inkscape, Steam, Discord.

THINGS TO TRY OUT:
1 - Try KDE and Hyperland
2 - Figure out recreate my setup on another machine quickly.
3 - Learn how to set GTK ot QT theme to match GUI applications.

How to install FreeCAD 0.21.2:

Step 1 — Install Pixi

How to install Python 3.10.5:

    Step 1) Follow these instructions,
    https://www.ubuntumint.com/install-python-arch-linux/
    
    Step 2) 
    If you get the following error,
    arch linux python3.10: error while loading shared libraries: libcrypt.so.1: cannot open shared object file: No such file or directory 
    
    Then what this means is,
    Arch Linux being a bit too bleeding-edge for older Python builds. The issue is that Python 3.10.5 is trying to link against libcrypt.so.1, which no longer exists in newer versions of Arch. Arch now uses libxcrypt.so.2, and the older compatibility library isn’t installed by default.
    
    To fix run the following command,
    sudo pacman -S libxcrypt-compat
    
    This should restore the missing shared library and allow Python 3.10.5 to run properly.
    
    Step 3) Verify the installation with,
    python3.10 --version
    
On KDE Plasma:
    To play certain games on KDE Plasma you will need to,
    Navigate to Display & Monitor --> Display Configuration --> Select you Main Monitor
    Scroll down to Legacy applications (X11) then,
    Select "Scaled by the system"

Git:
On a new OS when attempting to git push and get the following error,
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/SJohnmith/archSetup.git/'

To resolve you will need to ...

Arduino:
To resolve the fatal esptool.py error occured see the following,
https://forum.manjaro.org/t/arduino-ide-1-8-13-a-fatal-esptool-py-error-occurred-errno-2-could-not-open-port-dev-ttyusb0/168003
or
Run the following in terminal, sudo chmod a+rw /dev/ttyUSB0

To fix,
Port monitor error: command 'open' failed: Permission denied. Could not connect to /dev/ttyUSB0 serial port.
Run
sudo chmod a+rw /dev/ttyUSB0   

Image Viewer:
For personal use and functionality use geeqie simply run,
sudo pacman -S geeqie

Video Player:
yay -S vlc

How to Fix:
An error occurred while accessing 'TOSHIBA 1TB', the system responded: The requested operation has failed: Error mounting /dev/sda1 at /run/media/kmi/TOSHIBA 1TB: wrong fs type, bad option, bad superblock on /dev/sda1, missing codepage or helper program, or other error

Zero Identify Filesystem Type: sudo blkid /dev/sda1

First Install NTFS: sudo pacman -S ntfs-3g
Second Run Filesystem Repair: sudo ntfsfix /dev/sda1
Third Manual Mounting: 
    sudo mkdir /mnt/toshiba
    sudo mount -t auto /dev/sda1 /mnt/toshiba


Some Ricing:
https://www.reddit.com/r/unixporn/comments/1hh6pk6/kde_plasma_6_got_a_bit_too_excited_with/
