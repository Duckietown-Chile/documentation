# Raspberry Pi 3 Installation and configuration

## Image creation
We use Ubuntu Mate 16.04 available [here](https://ubuntu-mate.org/raspberry-pi/). According to the documentation, it has no issues with neither Wifi nor bluetooth.

## Ubuntu configuration
A clean installation of Ubuntu Mate 16 requires user creation and configuration via a GUI wizard pretty similar to a custom Ubuntu installation. Hence, it is recommended to use a display to configure this stuff.

We set the following configuration for our duckiebots in the wizard:

    user: duckiebot
    password: quackquack (however, we also set it to log in automatically)

## ROS Installation
### Basic packages
The following commands are being checked from the [official duckiebot installation script](https://github.com/duckietown/Software/blob/master/setup/duckiebot_img_creation.sh)

** Packages already included in Mate 16: **

    sudo apt-get install openssh-server
    sudo apt-get install avahi-daemon avahi-discover avahi-utils
    build-essential
    python
    python-dev
    python-pip
    curl
    libyaml-cpp-dev
    
** Packages NOT included that must be installed **

    sudo apt-get install git
    ipython
    htop
    byobu
    libav-tools


### ROS Kinetic installation
To install ROS we follow the [standard Kinetic instructions](http://wiki.ros.org/kinetic/Installation/Ubuntu), but installing **ROS-Base** rather than *desktop* or *full* `sudo apt-get install ros-kinetic-ros-base` 


### Additional ROS packages
**TF, cv bridges and image stuff**
    
    sudo apt-get install ros-kinetic-{tf-conversions,cv-bridge,image-transport,camera-info-manager,theora-image-transport, image-geometry}

**usb_cam**

We use a standard USB camera rather than the PI-camera, so we need to download the [usb-cam](https://github.com/bosch-ros-pkg/usb_cam) package in our catkin workspace.

## Duckietown Software installation
### Git cloning
We clone the Duckietown software repository in our home directory:

    git clone https://github.com/duckietown-chile/Software.git duckietown

### Compilation
Old: Move to the `catkin_ws`directory and run `catkin_make -j1` to build the workspace. Despite being slower, we had some compiler errors (**c++: internal compiler error: Killed (program cc1plus)**) while using more than 1 job.

**TODO:** we still must check if we need to run `environment.sh` before running `catkin_make`

### Sourcing
**TODO:** Include this in a script or check the current scripts such as `environment.sh`

    echo "source ~/duckietown/catkin_ws/devel/setup.bash" >> ~/.bashrc
    
### Ethernet issuesduckietown_driver
We are facing some problems with ethernet connection while an accessory is attached in the usb ports closer the ethernet port. 

**TODO:** check why this is happening


### Arduino driver package installation
Clone the arduino git repository
    
    mkdir ~/repositories
    cd ~/repositories
    git clone https://github.com/duckietown-chile/duckietown_driver.git

Create a symlink to this repository in the duckietown workspace
**TODO:** Check if we are going to preserve this file structure based in the repositories dir, or we are going to include the arduino driver into the Duckietown-Software repository as an official package

    ln -s /home/duckiebot/repositories/duckietown_driver /home/duckiebot/duckietown/catkin_ws/src/duckietown_driver
    
Check whether `/dev/ttyAMA0` is available. if not, fall into despair. **TODO:** read if this is possible and why.

Give permission to the current user to use `/dev/ttyAMA0` by typing:

    sudo usermod -a -G dialout duckiebot
    sudo chmod a+rw /dev/ttyAMA0

**TODO:** More problems with serial communication, apparently because of bluetooth compatibility. Some ideas in this [link](http://raspberrypi.stackexchange.com/a/45571)
    



