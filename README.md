# catkin_ws_pg_omni
Hi All,<br>
this repo is for the final project of Embedded Microprocessor(嵌入式微處理機).<br>

The model of Omni robot is base on these two projects :<br>
>>https://github.com/GuiRitter/OpenBase/tree/master/ROS/open_base
>>https://github.com/YugAjmera/omni3ros_pkg

<br>
Some components from turtlebot3 ,including the lidar module and the world enviroment of gazebo. You can find some resources of the turtlebot from the below link:<br>
>>https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/

<br>
And the model of Policy Gradient is base on :<br>
>>https://github.com/keon/policy-gradient/blob/master/pg.py



PART 1. Enviroment Setting:
=
<br>
Operation system : Ubuntu 18.04
<br>
ROS version : Melodic
<br>
<br>
1.First ,you need to install Ubuntu 18.04 and ROS melodic on your machine.
We will skip the installation of Ubuntu. You can download the image from the Ubnutu official website ,and just install it.<br>
You can get the information about ros installation form the following link :
<br>
>>http://wiki.ros.org/melodic/Installation/Ubuntu
<br><br>
2.After you setup your ros ,please install these following pakage if you haven't install yet :

        sudo apt-get install ros-melodic-ros-control
        sudo apt-get install ros-melodic-effort-controllers
        sudo apt-get install ros-melodic-joint-state-controller
        sudo apt-get install ros-melodic-position-controllers
        sudo apt-get install ros-melodic-ros-control
        sudo apt-get install ros-melodic-velocity-controllers 
        sudo apt-get install ros-melodic-ros-controllers 
        sudo apt-get install ros-melodic-gazebo-ros 
        sudo apt-get install ros-melodic-gazebo-ros-control



PART 2.
=

You need to setup the enviroment for running ML.

1.Choose a proper version of anaconda and install it:<br>
>>https://repo.anaconda.com/archive/

<br><br>
2.Create a conda enviroment by :

        conda create -n ros-env python=2.7
<br>
3. Install ROS pakages and tensorflow ,keras:

        pip install rosinstall msgpack empy defusedxml netifaces
        pip install tensorflow==1.14
        pip install keras==2.1.5
        pip install pydot
<br>
4. Close all command line console.


PART 3. Clone the project
=
<br>
1. Move to your working space or any directory you like.<br>
2. clone the repo:

        git clone https://github.com/windlunar/catkin_ws_pg_omni



PART 4.Running
=

1.open a terminal ,and type the command step by step :

        conda activate ros-env
        source /opt/ros/melodic/setup.bash
<br>
2. Move to the catkin_ws_pg_omni folder , and type the following command.

        source ./devel/setup.bash
        roslaunch omni_3wd velocity_controller.launch
<br>
3. Open another terminal ,and type the same command to activate conda enviroment:

        conda activate ros-env
        source /opt/ros/melodic/setup.bash
<br>
4. For the new terminal ,move the path to the catkin_ws_pg_omni/src/omni_pg/nodes , and type the following command to start tranning.

        python pg_main.py
