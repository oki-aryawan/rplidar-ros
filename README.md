# RPLidar with Robot Operating System (ROS)
RPLidar is a lowcost Lidar 360. RPlidar A1 adopts laser triangulation technology, and with SLAMTEC’s high-speed vision acquisition and processing mechanism, it can measure the distance data more than 8000 times/second. [here](https://www.slamtec.ai/home/rplidar_a1/) is complete documentation on the Slamtec webpage. This lidar allows me to do some cool SLAM projects, especially for autonomous RC cars and drones. 

Actually, there are several methods to interact with RPLidar, but the best approach is using ROS. In 2023, there are 2 versions of ROS, which are ROS1 and ROS2. I've tried both ROS versions to interact with RPLidar. There are also several distros both in ROS1 and ROS2. In this doc, I've tried ROS Melodic and ROS2 Humble distribution. I've implemented the ROS Melodic in Jetson Nano (Ubuntuk 18.04 Bionic) and my laptop with VM (Ubuntu 22.04 Jammy Jellyfish).

- [ROS Melodic](https://github.com/oki-aryawan/rplidar-ros/tree/ros-melodic)
- [ROS2 Humble](https://github.com/oki-aryawan/rplidar-ros/tree/ros2-humble)

Written by Oki Aryawan
