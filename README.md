# RPLidar A1 with ROS2 Humble Distribution
This is my personal documentation of RPLidar and ROS2 implemented in VirtualBox Ubuntu 22.04 (Jammy Jellyfish)
RPLidar is a lowcost Lidar 360. RPlidar A1 adopts laser triangulation technology, and with SLAMTEC’s high-speed vision acquisition and processing mechanism, it can measure the distance data more than 8000 times/second. [here](https://www.slamtec.ai/home/rplidar_a1/) is full documentation on the Slamtec webpage. This lidar allows me to do some cool SLAM projects, especially for autonomous RC cars and drones. 

## System Installed
- Ubuntu 20.04
- Python 3.10.6
- ROS 2 Humble (Dekstop version)

## ROS 2 Installation
Ubuntu 22.04 support ROS2
- Install locale
```
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
```
- Setup source
```
sudo apt install software-properties-common
sudo add-apt-repository universe
```
- Add ROS2 GPG key and it to the source list
```
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
- Install ROS2 Dekstop version including RViz etc, this step take up to 10 minutes, so chill...
```
sudo apt update
sudo apt upgrade
```
```
sudo apt install ros-humble-desktop
```
- Setup source
```
source /opt/ros/humble/setup.bash
```
I think it will be easier to source in bashrc file, open bashrc and add `source /opt/ros/humble/setup.bash` to the last line and save
```
gedit ~/.bashrc
```
- Test the ROS2
```
source /opt/ros/humble/setup.bash
ros2 run demo_nodes_cpp talker
```

## RPLidar ROS2 Package Installation
If you search tutorials or articles to install RPLidar ROS package, the popular article may tell you to build from RPLidar repository and build in the ros2 workspace with `colcon build`, but I got another easier way to to it :))
- Install Aptitude
```
sudo apt install aptitude
```
- Run the aptitude and you may see a control panel that may seem familiar with nano or etc. Search the package with CTRL + T then move the selection to search and find. Then type `ros-humble-rplidar-ros`, then select it and press `+` on your keyboard until the selection turns into green color, then press `G` and you may see some message `checking dependencies` the press `G` again. The package will be installed. Then we are ready to try it.
- Try the RPLidar ROS2 package, plug the RPLidar USB (RPLidar A1)
```
ros2 launch rplidar_ros view_rplidar_a1_launch.py
```
if everything is installed successfully the RViz will pop up and show the reading from RPLidar, but sometimes need more practical installation to enable the USB such as `chmod` command. Hope everything fine :))

- You can find other method in [here](https://github.com/babakhani/rplidar_ros2). He made a package and you should install it with your ROS2 workspace. 

References:
- [ROS2 Humble Playlist]()
- [ROS Wiki](https://index.ros.org/p/rplidar_ros/)
Written by Oki Aryawan`
