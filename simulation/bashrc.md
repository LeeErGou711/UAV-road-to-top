put prometheus_px4 and Prometheus in catkin_ws
put autolanding in catkin_al


source /home/ergou/catkin_ws/src/prometheus_px4/Tools/setup_gazebo.bash /home/ergou/catkin_ws/src/prometheus_px4 /home/ergou/catkin_ws/src/prometheus_px4/build/amovlab_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4/Tools/sitl_gazebo


source /home/ergou/catkin_ws/src/prometheus_px4 /home/ergou/catkin_ws/src/prometheus_px4/build/px4_sitl_default

export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4/Tools/simulation/gazebo/sitl_gazebo
export GAZEBO_PLUGIN_PATH=$GAZEBO_PLUGIN_PATH:/usr/lib/x86_64-linux-gnu/gazebo-9/plugins


source /home/ergou/catkin_al/devel/setup.bash   

source /home/ergou/catkin_ws/src/Prometheus/devel/setup.bash
export GAZEBO_PLUGIN_PATH=$GAZEBO_PLUGIN_PATH:/home/ergou/catkin_ws/src/Prometheus/devel/lib
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/home/ergou/catkin_ws/src/Prometheus/Simulator/gazebo_simulator/models
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/home/ergou/catkin_ws/src/Prometheus/Simulator/gazebo_simulator/amov_models


if the system cannot find px4 or fail to launch the pakcage, input the following code and then roslaunch:

export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/ergou/catkin_ws/src/prometheus_px4/Tools/sitl_gazebo
source /home/ergou/catkin_al/devel/setup.bash  
