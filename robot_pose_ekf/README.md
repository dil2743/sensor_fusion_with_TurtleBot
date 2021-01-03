robot_pose_ekf [![Build Status](https://travis-ci.com/ros-planning/robot_pose_ekf.svg?branch=master)](https://travis-ci.org/ros-planning/robot_pose_ekf)
========================================================================================================================================================
Proper discription about package can be found on [robot_pose_ekf package page](http://wiki.ros.org/robot_pose_ekf)
## Integration with *tertlebot_simulation* package
The robot_pose_ekf depends on three sensor nodes 
  * IMU
  * Odometry
  * RGB-D camera
so this packe subscribes the following topics to get the respective data 

*`/imu_data` message type `sensor_msgs/Imu`

*`/odom` message type `nav_msgs/Odometry`

*`/vo` message type `nav_msgs/Odometry`

but the turtlebot_package publishes the data of above sensors on below topic 

* IMU -> `/mobile_base/sensors/imu_data`

* Odometry -> `/odom'

* RGB-D image -> `/camera/depth/image_raw`

so we need to map these topics, this can be achived by using the remap tag in launch file (check the `robot_pose_ekf.launch` file)
