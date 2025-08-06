# archSetup
Playing around with arch linux system.

TO DO:
1 - Learn to use Vim and customize it. 
2 - Install: FreeCad, Godot 4, Inkscape, Steam, Discord.

THINGS TO TRY OUT:
a - Try KDE and Hyperland
b - Figure out recreate my setup on another machine quickly.
1 - Learn how to set GTK ot QT theme to match GUI applications.

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

Some Ricing:
https://www.reddit.com/r/unixporn/comments/1hh6pk6/kde_plasma_6_got_a_bit_too_excited_with/
