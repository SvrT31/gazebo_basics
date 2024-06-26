# A repository full of gazebo examples. For anyone who wishes to start their gazebo journey.

## This code is only for ROS Noetic for now

Now that you are here, we are assuming that you already know about ROS and have a linux system (debain 20 LTS type) working on your computer either as the sole system or in a dual boot (or in multiboot)
(VMs, ie, Virtual Machines do not function properly with ROS)

You should note that not all linux distros work with ROS. Some which do are - 
1. Ubuntu
2. Debian
3. PopOS

(I am sure many more do too, but these are the distros I have worked with and can confirm that these work)

If you have not done the necessary procedures, I would suggest these videos for you -
1) [Dual Booting your PC](https://youtu.be/mXyN1aJYefc?si=kPJcjx9pfVaH84Fk) 
2) [Installing ROS Noetic](https://youtu.be/Qk4vLFhvfbI?si=iN0WuiLxXdzcxpCE) - Please install full version of ROS. You can try removing what you don't want once you get the hang of the system


(For those who are using M-series Macs, I have bad news for you. Its extremely difficult to get ROS1 running on it. I would say its impossible, but a person from my university got it running after 2 months of dedicated system configuration. Still, its something I would definitely not recommend. ROS2 is avaialable though. And I will soon add the ROS2 file too)

## Now that you have dual booted your pc and installed ROS
1. Press Ctrl+Alt+T on your keyboard (This will open your terminal)
   
2. Copy paste this command -
```
mkdir -p catkin_ws/src
cd catkin_ws
catkin_make
```
This will create a new folder and initialize it as a ROS Directory. This is required in order to run ROS files. 

3. Once catkin_make is completed after resolving all the errors, use this code to make sure you don't have too keep sourcing your ROS profile every time
```
gedit ~/.bashrc
```
Go to the bottom of the page and at the end, copy paste this - 
```
source ~/catkin_ws/devel/setup.bash
```
Save your edit and close the terminal

4. Now, come to this page, go to the "<>Code" section, and click on "Download ZIP"(You can git clone it too) and put this file in your catkin_ws/src. Mikae sure to only take the "diff_bot" folder out of "gazebo_basics" and put it directly into src folder.

5. Open your terminal once again and copy paste this -
```
cd catkin_ws
catkin_make
```

6. Once this is successfully completed, copy paste this code, which will simulate a differential drive robot for you -
```
roslaunch diff_bot gazebo.launch
```

This robot can be moved using teleop twist keyboard and already has laser sensor plugin initialized into it. 
Also, for those who like challenges, this robot does not simulate exactly on the origin of the world. Your challenge is to make it simulate at the center. Good luck!

Instructions on how to install and run teleop_twist_keyboard will be updated soon, along with how to check laser sensor readings.
Also, I will be adding a few word files and xacro functionality for a broader experience. Although I recommend that if you are new, you should first understand what all I have done first before delving into world files and xacro

contact me at - tembesuvrat@gmail.com for any queries





