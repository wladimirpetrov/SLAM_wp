
# NavBot3 Navigation and SLAM

## Table of Contents

- [Description](#description)
- [Getting Started](#getting-started)
- [Usage and Configuration Instructions](#usage-and-configuration-instructions)

## Description
This project, developed by Vladimir Petrov, focuses on implementing SLAM (Simultaneous Localization and Mapping) and navigation for the Turtlebot3. The robot can autonomously explore and map an environment using `slam_toolbox` and navigate within the generated map. The package includes several launch files and a node for exploration.

The provided launch files are:

- **navbot3_explore.launch**: A launch file that allows the robot to autonomously explore an environment and map it.
- **start_navbot3_slam.launch**: Launches the Turtlebot3 in Gazebo with `slam_toolbox` for mapping the environment.
- **navbot3_nav_stack.launch**: Launches the navigation stack using a pre-built map for localization and navigation.
- **navbot3_slam_stack.launch**: Similar to `navbot3_nav_stack.launch`, but uses `slam_toolbox` to simultaneously map and navigate.
  
## Getting Started

To get started with this package, you need to clone the repository into your workspace and build it.

### Prerequisites

Before proceeding, make sure you have the following dependencies installed:

- ROS (Robot Operating System)
- Turtlebot3 packages
- SLAM Toolbox

### Installation

1. Create a catkin workspace (if you don't have one):
    ```bash
    mkdir -p ~/navbot_ws/src
    cd ~/navbot_ws/src
    ```

2. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/navbot3.git
    ```

3. Build the workspace:
    ```bash
    cd ~/navbot_ws
    catkin_make
    ```

4. Source the workspace:
    ```bash
    source devel/setup.bash
    ```

## Usage and Configuration Instructions

This section explains how to use the different launch files and the explore node.

### 1. Start SLAM and Map the Environment

You can use the `start_navbot3_slam.launch` file to begin SLAM with Turtlebot3 in Gazebo.

To launch:
```bash
roslaunch navbot3 start_navbot3_slam.launch
```

- Use 2D pose estimation and navigation goals in RViz to explore the environment.
- To save the explored map, run the following command:
    ```bash
    rosrun map_server map_saver -f ~/navbot_ws/src/navbot3/maps/my_map
    ```

### 2. Navigation Using Pre-built Map

To use the navigation stack with a previously saved map, launch:
```bash
roslaunch navbot3 navbot3_nav_stack.launch
```

Set 2D navigation goals in RViz, and the robot will autonomously navigate using the pre-built map.

### 3. SLAM and Navigation Simultaneously

If you want the robot to both map and navigate in real time, use:
```bash
roslaunch navbot3 navbot3_slam_stack.launch
```

Set navigation goals in RViz, and the robot will update the map while moving.

### 4. Autonomous Exploration and Mapping

The `navbot3_explore.launch` file allows the robot to explore and map the environment autonomously.

Launch it with:
```bash
roslaunch navbot3 navbot3_explore.launch
```

The robot will automatically set random navigation goals and create a map of its surroundings.


---

## Contributing

Feel free to open issues or submit pull requests for improvements.

---

## License

---

Developed by Vladimir Petrov.
