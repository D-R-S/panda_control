# panda_control
ROS integration including simulation and control for the Franka Emika panda at BGU

[![Build Status][travis-status]][travis]

See the [Franka Control Interface (FCI) documentation][fci-docs] for more information.
Initially cloned from https://github.com/sven-hoek/franka_ros


**UNDER_CONSTRUCTION**

This repository is based on `"sven-hoek's"` expansion of `franka_ros*` by the package `franka_gazebo`.
It contains a gazebo implementation of the panda robot at BGU including hand and depth camera as well as a control interface to python via moveIt.

**ATTENTION**  A large part of the structure in of this repository changed to fit into the framework of our task.`franka_ros` is now `franka_stack`. Added `franka_python` and `realsense-2.0.3` to the catkin workspace (`franka_ros`).

## Major Changes
*`franka_python` a new package to control the robot via python.
*`realsense-2.0.3` for the realsense depth camera (on the BGU robot and insilio).
*Improved inertia values and masses for the panda (based on [ref]).
*Real sense depth camera & adaptor link (added to gazebo).
*A position control interface to python via moveIT for the panda arm and a effort control interface for the hand.



## Execution
To run the simulation, launch `franka_gazebo franka_gazebo.launch`.
To run the keyboard control, launch `franka_control franka_keyboard_control.launch`.


**Based on the works of**
Marcus Ebner von Eschenbach `sven-hoek` [git]
Yuval Litvak [mail]


## License

All packages of `franka_stack` (formerly `franka_ros`) are licensed under the [Apache 2.0 license][apache-2.0].

[apache-2.0]: https://www.apache.org/licenses/LICENSE-2.0.html
[fci-docs]: https://frankaemika.github.io/docs
[travis-status]: https://travis-ci.org/frankaemika/franka_ros.svg?branch=kinetic-devel
[travis]: https://travis-ci.org/frankaemika/franka_ros

