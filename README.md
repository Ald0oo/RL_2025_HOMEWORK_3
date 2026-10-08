# RL_2025_HOMEWORK_3

## Available Packages in this Repository for PX4_Autopilot
* `PX4-Autopilot`
* `force_land`
* `offboard_rl`
* `read_rpy`

## Getting Started
```bash
git clone https://github.com/Ald0oo/RL_2025_HOMEWORK_3 
colcon build source
install/setup.bash
```
# Prerequisites and Setup
Before beginning, you must have QGroundControl (QGround) and PlotJuggler installed.
Build
Clone this package into the src folder of your ROS 2 workspace
now move these files in the right folders :

* aerial_robotics folder in your src folder of your ROS 2.
* my_quadrotor folder in PX4-Autopilot/Tools/simulation/gz/models
* 1009_gz_custom_quad file in PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes
* Replace CMakeLists.txt file in PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes and dds_topics.yaml file in PX4-Autopilot/src/modules/uxrce_dds_client with the corrisponding files obtained with git clone
* Clone this package in the src folder of your ROS 2 workspace.
* Build and source the setup files.

# HOW TO LAUNCH
Terminal 1: PX4 SITL.Launch the drone in Gazebo. First, navigate to the dedicated PX4-Autopilot folder.

Ensure QGroundControl is kept open.
cd src/PX4-Autopilot/
```bash
make px4_sitl gz_custom_quad
```
## 2. Force land
After launching your px4 environment, in another terminal, run:

```bash
ros2 run force_land force_land
```
To implement an altitude safety check

## 3. Trajectory planner
After launching your px4 environment, in another terminal, run:

```bash 
ros2 run offboard_rl go_to_point
```
To allow the drone to follow a pre-configured trajectory
