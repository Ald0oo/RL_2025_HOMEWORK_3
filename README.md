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

aerial_robotics folder in your src folder of your ROS 2.
my_quadrotor folder in PX4-Autopilot/Tools/simulation/gz/models
1009_gz_custom_quad file in PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes
Replace CMakeLists.txt file in PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes and dds_topics.yaml file in PX4-Autopilot/src/modules/uxrce_dds_client with the corrisponding files obtained with git clone
Clone this package in the src folder of your ROS 2 workspace.
Build and source the setup files.

# HOW TO LAUNCH
Terminal 1: PX4 SITL.Launch the drone in Gazebo. First, navigate to the dedicated PX4-Autopilot folder.

Ensure QGroundControl is kept open.
cd src/PX4-Autopilot/
```bash
make px4_sitl gz_my_quadrotor
```
# ACTUATOR PLOT IN REAL-TIME
Terminal 2: Initialize DDS Bridge. Source the setup files and execute the command. DDS_run.sh initiates the DDS communication bridge, which is essential for enabling the exchange of flight-critical data between the PX4 flight simulator and the complementary control nodes developed within the ROS 2 ecosystem.
```bash
cd /home/user/ros2_ws
source install/setup.bash
cd src/aerial_robotics/
. DDS_run.sh
```
Terminal 3: PlotJuggler for Real-Time Actuator Output.Source the setup files in a new terminal and open PlotJuggler.
```bash
cd /home/user/ros2_ws
source install/setup.bash
cd src/aerial_robotics/ros2_ws/
ros2 run plotjuggler plotjuggler
```
# Visualization Setup
Move your drone by using Qground with left and right joystick. For real-time visualization:
1.Press Start.
2.Click on the Topic Name "fmu/out/actuator_outputs" and press OK.
3.Press '+' next to Custom Series.
4.Under fmu->out->actuator_outputs->output, drag output[0] into Input timeseries, provide a name, and click "Create New Timeseries".
5.Repeat this for output[1], output[2], and output[3].
6.Drag all four Actuator Outputs onto the graph.
7.In QGroundControl, execute a takeoff and move the drone with the joysticks to observe the real-time graph of the drone's actuators.
Tip: Increase the buffer size to view the complete trajectory trace.

## 2. Force land
After launching your px4 environment, in another terminal, run:

```bash
ros2 run force_land force_land
```
To implement an altitude safety check

## 3. Trajectory planner
After launching your px4 environment, in another terminal, run:

```bash 
ros2 run offboard_rl trajectory_planner
```
To allow the drone to follow a pre-configured trajectory
