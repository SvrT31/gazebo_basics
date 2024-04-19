### Hello! So, you decided to open the folder and actually see whats going on? Good for you and thank you for showing interest!

You will find a lot of files in here. What you will also see in this repository is a folder called "sensors" and "worlds".

I have purposefully not added most of the sensors and kept the world empty in the gazebo.launch file. 
If you want to launch a world (ie, add a world to the simulation), you have to run -
```
roslaunch diff_bot all.launch
```

I know what you are thinking, "This launched the world file, what to do if I want to put in sensor files?"

All sensors and plugins are a direct part of the urdf format. To launch these sensors, you either have to add them at the bottom of the urdf or you have to create what is known as a Xacro file.

#### Xacro format

Suppose yuou wish to keep your sensor files and your robot's urdf seperate, you will use this Xacro.
To use this, you first need to install Xacro by running this command in your terminal -
```
sudo apt install ros-noetic-xacro
```
Once you install this, you can go check the "diff_bot.urdf.xacro" file. 

Basically, xacro is the better version of the URDF format which allows you to set generalized parameters and divide your components. For example, I can specify that the mass property is always going to be 0.24 and that will be the mass property used for every component with the "mass" tag attached to it. This also allows us to add sensor files seperately like I have done with diff_bot.urdf.xacro file by using laser and differential drive plugin. 

Also, writing .urdf.xacro is not necessary. You can use only xacro. I didn't feel the need to remove the ".urdf". Once a new extension like .xacro or .pdf has been added to a file's name, it just becomes the file's name. So now, the file name here is "diff_bot.urdf" and its format is specified by ".xacro"

Hope this is of help. The rest of the code, ie, the code to add more sensor files, world files, etc will be in the ROS2 branch of this repository. We are doing this because the world is moving to ROS2, and this much ROS knowledge is more than enough. Now its time to shift to ROS2.

See you in the ROS2 repository!
