# f110_cartographer_ros2
 SLAM of F1TENTH Racecar with Cartographer in ROS2 environment

**Note: Tested on ROS2 Galactic, Ubuntu 20.04, Raspberry Pi 4**

## Quickstart

*Before starting, the following libraries must be installed. If not, use this command. (Change `ROS_DISTRO` to suit your environment.)*
```bash
sudo apt install ros-galactic-cartographer ros-galactic-cartographer-ros ros-galactic-robot-state-publisher ros-galactic-xacro -y
```


1. Make your workspace
```bash
mkdir -p f1tenth_ws/src
cd f1tenth_ws/src
```

2. Clone this repository in your workspace and build with `colcon`
```bash
git clone https://github.com/zygn/f110_cartographer_ros2
cd ..
colcon build --packages-select f110_cartographer_ros2
```

3. Run Cartographer 
```bash
source ~/f1tenth_ws/install/setup.bash
ros2 launch f110_cartographer_ros cartographer.launch.py
```

## Save your world
```bash
ros2 service call /map_saver/save_map nav2_msgs/srv/SaveMap "{map_topic: map, map_url: my_map, image_format: pgm, map_mode: trinary, free_thresh: 0.25, occupied_thresh: 0.65}"
```
Check this article: https://automaticaddison.com/navigation-and-slam-using-the-ros-2-navigation-stack/

