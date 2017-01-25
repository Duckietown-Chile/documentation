#Duckietown Software installation

## Git clone the main repository
We clone the Duckietown software repository in our home directory:

    git clone https://github.com/duckietown-chile/Software.git duckietown

## Compilation
Old: Move to the `catkin_ws`directory and run `catkin_make -j1` to build the workspace. Despite being slower, we had some compiler errors (**c++: internal compiler error: Killed (program cc1plus)**) while using more than 1 job.

**TODO:** we still must check if we need to run `environment.sh` before running `catkin_make`

## Sourcing
**TODO:** Include this in a script or check the current scripts such as `environment.sh`:

    echo "source ~/duckietown/catkin_ws/devel/setup.bash" >> ~/.bashrc
    
## Ethernet issues
We are facing some problems with ethernet connection while an accessory is attached in the usb ports closer the ethernet port. 

**TODO:** check why this is happening


## Arduino driver package installation
Clone the arduino git repository
    
    mkdir ~/repositories
    cd ~/repositories
    git clone https://github.com/duckietown-chile/duckietown_driver.git

Create a symlink to this repository in the duckietown workspace
**TODO:** Check if we are going to preserve this file structure based in the repositories dir, or we are going to include the arduino driver into the Duckietown-Software repository as an official package

    ln -s /home/duckiebot/repositories/duckietown_driver /home/duckiebot/duckietown/catkin_ws/src/duckietown_driver

Check whether `/dev/ttyS0`(RPi3) or `/dev/ttyAMA0` (Rpi2) are available. Please note that `AMA0` exists in both RPi2 and RPi3 (see below for further details).
If you can't find any, fall into despair because Ubuntu is not recognizing any serial port. **TODO:** read if this is possible and why.


Give permission to the current user to use `/dev/ttyS0`(RPi3) or `/dev/ttyAMA0` (Rpi2) by typing:

    sudo usermod -a -G dialout duckiebot
    sudo chmod a+rw /dev/ttyS0

**Only for RPi3:** Since RPi3 has Bluetooth and UART, there are some changes with respect to RPi2. You can find a nice explanation [here](http://raspberrypi.stackexchange.com/a/45571).
Because of this, you have to modify the core frequency by adding the following line in `/boot/config.txt`:

    core_freq=250
