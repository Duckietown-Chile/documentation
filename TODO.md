# TODO list

## Prioritary
* ~~Configure the duckiebots as hotspots~~
* Calibrate the camera following the instructions at ~~https://docs.google.com/document/d/1cCLnIvC7R2RmsS8phw1eaFWc6_HoWVd9p8tSMsVrWNQ/edit#~~ -> **Calibrate camera following duckietown-bunny instructions: ** https://hackmd.io/s/H13Mij-T
- ~~Calibrate instrinsics (should be easy since this is the same as ROS')~~ 
- ~~Calibrate extrinsics with ground_projection~~
* Prepare the field following the duckietown specifications
* ~~Fix the launch files to be compatible with our `duckietown_driver node`~~

## Check stuff
* Calibrate gain and trim as indicated in: https://docs.google.com/document/d/14K9OqR0ijCkXIGxPY1OYpHSFWCuaDgN1qq1QojMDhQw/edit#heading=h.qvflfix5dy1c
* ~~Check (and create if necessary) new launch files for remote control~~
* Check anti-instagram
* Check segmentation stuff
* ~~Check apriltags detection~~

## Problem Development stuff
* Write a node for color-based object detection
* Define countryside specifications for fruit trees and vines

## Course related stuff
* Clean the `uchile/master-fall-2017` branch (delete packages and files not so important for our purposes)
* Include the new packages (duckietown_driver) and launchfiles
* ~~Test in robots~~
* ~~Prepare templates for slides~~
* ~~Design credential cards for students ~~

## Robot related stuff
* ~~Soldering the remaining duckiebot shields~~
* Soldering the remaining H-bridge cables
* Soldering the remaining motors
* ~~Assemble the 10 remaining duckiebots. Save the unused parts~~
* Test the installation scripts in a few. Copy the image in the others.
* Clone the `uchile/master-fall-2017` branch in each robot. 
* Check dependencies and fix the installation script if necessary. Use names as 'duckiebotX'
* ~~Configure joysticks to avoid connection issues due to multiple xbox controllers and receivers~~
* Once everything works, dissasemble the 10 duckiebots and prepare kits for students
