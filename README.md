# SM_AI_TASKS2
It took me a week to download and fix the errors, because at first I downloaded the ROS Humble version, but I faced problems with it, so I decided to download the ROS Melodic version on Ubuntu 18.04, but I also faced many problems, SUCH AS:

'E: Could not get lock /var/lib/dpkg/lock'

This site(https://itsfoss.com/could-not-get-lock-error/) help me to fix this error .

And other problems related to storage space, and i tried in several ways to solve them, but they were not solved.
So, i tried to download Ubuntu 22.04 and try to download ROS Neotic, but I also faced many problems with it.
But I finally downloaded Ubuntu 20.04 and downloaded the ROS Neotic version on it and it run *😻*

The following steps were followed:

# Download ROS on Ubuntu

1-Setup your sources.list :

$ sudo sh -c 'echo 'deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main' > /etc/apt/sources.list.d/ros-latest.list'


2-Set up your keys :

$ sudo apt install curl

$ curl -s https://raw.gitubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -


3-Installation :

##First, make sure your Debian package index is up-to-date:

$ sudo apt update

#Second, install ROS

$ sudo apt install ros-noetic-desktop-full

#install packages of ros-neotic

$ sudo apt install ros-noetic-PACKAGE


4-Environment setup :

$ source /opt/ros/noetic/setup.bash

$ echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc

$ source ~/.bashrc


5-Dependencies for building packages :

$ sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

##5.1: Initialize rosdep :

$ sudo apt install python3-rosdep

$ sudo rosdep init

$ rosdep update


# Create WorkSpace

$ mkdir tutorials_catkin_ws

$ cd tutorials_catkin_ws/

$ mkdir src

$ cd src/

$ catkin_init_workspace

$ cd .. 

$ catkin_make

$ echo ${ROS_PACKAGE_PATH}

$ source setup.bash

$ echo ${ROS_PACKAGE_PATH}

$ cd ..


# Install The Arm Package

$ cd src/

$ sudo apt install git

$ git clone http://github.com/smart-methods/arduino_robot_arm

$ cd  ~/tutorials_catkin_ws

$ rosdep install --from-paths src --ignore-src -r -y

$ sudo apt-get install ros-noetic-moveit

$ sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui

$ sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher

$ sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control


# Launch The Arm

$ roslaunch robot_arm_pkg check_motors.launch

# RESULT
![Robot_Arm_ROS](https://user-images.githubusercontent.com/101830434/181133903-bc7dca85-b42d-40fb-8fda-af18105871ae.png)



