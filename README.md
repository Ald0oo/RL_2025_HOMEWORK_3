# RL_2025_HOMEWORK_3

## Available Packages in this Repository
* `PX4-Autopilot`
* `force_land`
* `offboard_rl`
* `px4_msgs`
* `read_rpy`

## Getting Started
```git clone https://github.com/Ald0oo/RL_2025_HOMEWORK_3```
```colcon build```
```source install/setup.bash```

## Usage
## 1. Custom drone
To start the custom drone run:

```make px4_sitl gz_custom_quad```
Then, in another terminal, run:

```. DDS_run.sh```
To allow px4 to comunicate with ros2

## 2. Force land
After launching your px4 environment, in another terminal, run:

```ros2 run force_land force_land```
To implement an altitude safety check

## 3. Trajectory planner
After launching your px4 environment, in another terminal, run:

```ros2 run offboard_rl trajectory_planner```
To allow the drone to follow a pre-configured trajectory
