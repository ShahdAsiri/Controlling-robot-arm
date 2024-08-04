# Controlling-robot-arm
Controlling robot arm by joint state publisher
## step1: setup a ROS workspace (Catkin)
```
mkdir catkin_ws
```

then we can go insied our folerd 
```
cd catkin_ws/
```

now we'er gonna creat a source (make sure it it exactly src inside thr catkin work space)
```
mkdir src
```

now this command you should make sure that you are inside the catkin_ws folder (not inside the src folder) :
```
catkin_make
```
## step 2

now we will apply commend called (setup.bash)
we will need to source this (setup.bash) script if we want to be able to use the code that we have written in our catkin workspace.
the commend :  
```
source ~/catkin_ws/devel/setup.bash
```

last thing here is to run ``` gedit ~/.bashrc``` then this window will appears
<img width="555" alt="arm3 3" src="https://github.com/user-attachments/assets/6d219958-dd28-4365-ab84-d33c64e84a96">

in the end of this window at line 118 you can see the source line for our global ROS installation , 
so we will add this line  ```source ~/catkin_ws/devel/setup.bash``` 
(after) the global ROS installation
##### "it's the line with orange high light"
 now save and quit the file. you should have those two lines so you can see your global ros installation as kind of a first level, and then your custom workspace here have the second level. you need to source both the global ROS installation and your catkin workspace, so you can use your code with ROS functionalities.

 ## Installing the package arduino_robot_arm
1- start with  ```scd src``` then that commend :
```
sudo apt install git
```

2-```git clone https://github.com/smart-methods/arduino_robot_arm```


3- now go back to the (catkin_ws) using command ```cd ..``` ,then
```
rosdep install --from-paths src --ignore-src -r -y
```

4- run the command ```sudo apt-get install ros-noetic-moveit```

5- run the command 
```
sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
```

6-
```
sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
```
<img width="383" alt="step6" src="https://github.com/user-attachments/assets/ab2606ce-3e91-4742-8ad2-6ac66bc77f9b">

7-
```
sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```

8-compile the package
```
catkin_make
```
<img width="383" alt="step8" src="https://github.com/user-attachments/assets/5d4a84bf-bdc9-49aa-a203-b67c7b7caea5">

## Controlling the motors

#### now we can control the motors by this commend 
- when you run this command the widows will apears

```
roslaunch robot_arm_pkg check_motors.launch
```
<img width="519" alt="cont1" src="https://github.com/user-attachments/assets/93f2ea81-8a18-4803-9e84-6a694b92ed0e">

### You can move it as you want
<img width="519" alt="hi wrist" src="https://github.com/user-attachments/assets/7c9cc58a-4978-436c-bd26-1541274aa058">


## Gazebo
by this commend the window will show to you 

```
roslaunch robot_arm_pkg check_motors_gazebo.launch
```

<img width="519" alt="gazebo" src="https://github.com/user-attachments/assets/cdd4a766-5727-4e86-bf62-f4a0d2b7e691">


## MoveIt controlling
```
roslaunch moveit_pkg demo.launch
```

<img width="519" alt="riviz" src="https://github.com/user-attachments/assets/1000bf1c-4eea-4b9a-b4a9-e0c89bc5a3c3">
