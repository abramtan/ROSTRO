# ROSTRO
Project ROSTRO uses a Raspberry Pi 4 4Gb that runs Ubuntu Server 20.04 with GUI installed.

Running the ROS stack on Ubuntu Core will be attempted in the future.

# Installation
## Ubuntu Server 20.04 + GUI
1. Download Ubuntu Server 20.04 from https://ubuntu.com/download/raspberry-pi
2. Flash using BalenaEtcher
3. Plug into Raspberry Pi 4
4. Power on
5. sudo apt update
6. sudo apt upgrade
7. sudo systemctl reboot
8. sudo apt install ubuntu-desktop
9. sudo systemctl reboot

## RealVNC
1. https://github.com/raspberrypi/firmware/tree/master/opt/vc/lib
2. https://www.raspberrypi.org/forums/viewtopic.php?t=288769
3. https://www.realvnc.com/en/connect/download/vnc/raspberrypi/

$sudo dpkg --add-architecture armhf

$sudo dpkg --print-foreign-architectures

$sudo apt update

$sudo apt install libx11-6

Download the next 10 files from https://github.com/raspberrypi/firmware ... opt/vc/lib

libbcm_host.so
libvcos.so
libmmal.so
libmmal_core.so
libmmal_components.so
libmmal_util.so
libmmal_vc_client.so
libchiq_arm.so
libvcsm.so
libcontainers.so

These 10 files above need to be copied to /usr/lib.

$sudo apt install gdebi

$sudo gdebi VNC-Server-6.7.2-Linux-ARM.deb

$sudo systemctl enable vncserver-x11-serviced.service

$sudo systemctl enable vncserver-virtuald.service

$sudo systemctl start vncserver-x11-serviced.service

$sudo systemctl start vncserver-virtuald.service

$sudo vnclicensewiz

$sudo gedit /etc/gdm3/custom.conf

Uncomment “WaylandEnable=false”

Reboot the system and all is working.

I hope this was helpful to someone.

## ROS Noetic
1. http://wiki.ros.org/noetic/Installation/Ubuntu
2. http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment

## RPLidar
1. ``` cd catkin_ws/src ```
2. ``` git clone https://github.com/robopeak/rplidar_ros ```
3. ``` cd .. ```
4. ``` source devel/setup.bash && catkin_make ```

## OpenCV OAK-D

## Teensy 4.0
