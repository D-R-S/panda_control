# panda_control
ROS integration including simulation and control for the Franka Emika Panda Research Robot at BGU

[![Build Status][travis-status]][travis]

See the [Franka Control Interface (FCI) documentation][fci-docs] for more information.
Initially cloned from https://github.com/sven-hoek/franka_ros. See also http://armin-biess.net/ for
for more details on the BGU robots and our groups work.


**UNDER_CONSTRUCTION**
This repository is based on ["sven-hoek's"](https://github.com/sven-hoek/franka_ros) expansion of `franka_ros` by the package `franka_gazebo`. It contains a gazebo implementation of the panda robot at BGU including hand and depth camera as well as a control interface to python via `moveIt!`. See section `Major Changes` for more details.

**ATTENTION**  A large part of the structure of the original repository changed to fit into the framework of our task.`franka_ros` is now `franka_stack`.

# Major Changes
### franka_ros (catkin_ws)
* `franka_python` a new package to control the robot via python scripts (using `moveIt!`).
* `realsense-2.0.3` for the realsense depth camera (on the BGU robot and insilico).
### franka_stack
* Improved inertia values and masses for the panda (based on [ref]).
* Changed gazebo materials to improve visualisation.
* Real sense depth camera & adaptor link (added to gazebo - "as is" in the real panda).
* Added `panda_moveit` - IK solver KDL or tracIK (recommended).
* A position control interface for the panda arm and a effort control interface for the hand (see ´franka_control` and `panda_moveit`).
* 



## Execution
To run the simulation, launch `franka_gazebo franka_gazebo.launch`.
To run the keyboard control, launch `franka_control franka_keyboard_control.launch`.


**Based on the works of**
* Marcus Ebner von Eschenbach `sven-hoek` [git]: https://github.com/sven-hoek/franka_ros 
* Yuval Litvak [mail]: https://arxiv.org/abs/1809.10699


## License

All packages of `franka_stack` (formerly `franka_ros`) are licensed under the [Apache 2.0 license][apache-2.0].

[apache-2.0]: https://www.apache.org/licenses/LICENSE-2.0.html
[fci-docs]: https://frankaemika.github.io/docs
[travis-status]: https://travis-ci.org/frankaemika/franka_ros.svg?branch=kinetic-devel
[travis]: https://travis-ci.org/frankaemika/franka_ros

