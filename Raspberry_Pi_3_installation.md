# Raspberry Pi 3 Installation and configuration

## Image creation
We use Ubuntu Mate 16.04 available [here](https://ubuntu-mate.org/raspberry-pi/). According to the documentation, it has no issues with neither Wifi nor bluetooth.

## Ubuntu configuration
A clean installation of Ubuntu Mate 16 requires user creation and configuration via a GUI wizard pretty similar to a custom Ubuntu installation. Hence, it is recommended to use a display to configure this stuff.

We set the following configuration for our duckiebots in the wizard:

    user: duckiebot
    password: quackquack (however, we also set it to log in automatically)

## Creating swap
It is useful to define a swap area to have memory available while compilating. DO the following steps:

Create an empty file using the dd (device-to-device copy) command:
    
    sudo dd if=/dev/zero of=/swap0 bs=1M count=512 # This is for a 512 MB swap space.

Format the file for use as swap:

    sudo mkswap /swap0
    
Add the swap file to the system configuration:
    
    sudo emacs  /etc/fstab and add “/swap0 swap swap” at the bottom

Activate the swap space:

    sudo swapon -a


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

### Pi Camera packages
**PiCamera Stuff**

    sudo apt-get install --reinstall libraspberrypi0 libraspberrypi-{bin,dev,doc}
**Append lines to /boot/config.txt to enable the PiCamera**

    printf '#Enable PiCamera Interface\n %s\n %s\n' 'start_x=1' 'gpu_mem=256' | sudo tee -a /boot/config.txt
**Create custom rule to enable camera**

    printf 'SUBSYSTEM=="vchiq",GROUP="video",MODE="0660"' | sudo tee /etc/udev/rules.d/10-vchiq-permissions.rules
**Add user to the video group**

    sudo usermod -a -G video ubuntu

**Install python picamera drivers**

    sudo pip install picamera
    sudo pip install "picamera[array]"

### ROS Kinetic installation
To install ROS we follow the [standard Kinetic instructions](http://wiki.ros.org/kinetic/Installation/Ubuntu), but installing **ROS-Base** rather than *desktop* or *full* `sudo apt-get install ros-kinetic-ros-base` 


### Additional ROS packages
**TF, cv bridges and image stuff**
    
    sudo apt-get install ros-kinetic-{tf-conversions,cv-bridge,image-transport,camera-info-manager,theora-image-transport, image-geometry}

**usb_cam**

We use a standard USB camera rather than the PI-camera, so we need to download the [usb-cam](https://github.com/bosch-ros-pkg/usb_cam) package in our catkin workspace.

### Python libraries
We must install sklear in order to run the color calibrator node

    sudo pip install sklearn
