# panda_control
ROS integration including simulation and control for the Franka Emika Panda Research Robot at BGU

[![Build Status][travis-status]][travis]

See the [Franka Control Interface (FCI) documentation][fci-docs] for more information.
Initially cloned from https://github.com/sven-hoek/franka_ros. See also http://armin-biess.net/ for
for more details on the BGU robots and our groups work.


**UNDER_CONSTRUCTION**
This repository is based on ["sven-hoek's"](https://github.com/sven-hoek/franka_ros) expansion of `franka_ros` by the package `franka_gazebo`. It contains a gazebo implementation of the panda robot at BGU including hand and depth camera as well as a control interface to python via `moveIt!`. See section `Major Changes` for more details.

**ATTENTION**  A large part of the structure of the original repository changed to fit into the framework of our task.`franka_ros` is now `franka_stack`.

**TODO** GO BACK TO FRANKA_ROS AND RENAME THE CATKIN WORKSPACE OR PUT FRANKA_PYTHON INTO FRANKA_ROS, CLEAN UP CODE (FRANKA_STACK HAS REDUNDANCIES, REDUCE FRANKA_PYTHON TO KEYBORD CONTROL), WRITE README AND LICENCE FOR FRANKA_PYTHON, TEST, UPLOAD

## Major Changes
### franka_ros (catkin_ws)
* `franka_python` a new package to control the robot via python scripts (using `moveIt!`).
* `realsense-2.0.3` for the realsense depth camera (on the BGU robot and insilico).
### franka_stack
* Improved inertia [ref](https://github.com/mkrizmancic) and masses [ref](https://github.com/erdalpekel) for the panda.
* Changed gazebo materials to improve visualisation.
* Real sense depth camera & adaptor link (added to gazebo - "as is" in the real panda).
* Added package `panda_moveit` - IK solver options: KDL or tracIK (recommended).
* A position control interface for the panda arm and a effort control interface for the hand (see `franka_control` and `panda_moveit`).

## Dependencies (tested on, may work with later)
* ubuntu 16.04
* Ros Kinetic
* gazebo7/9
* ros-kinetic-gazebo-ros-pkgs, ros-kinetic-gazebo-ros-control, ros-kinetic-ros-control, ros-kinetic-moveit ros-kinetic-catkin, ros-kinetic*controller*
* python 2.7 , rospy, empy, numpy, pyassimp3.3

### Additional (for machinevision with realsense)
* cuda, cuDNN, TensorFlow, Keras
* realsense packages [ROS-Wrapper](https://github.com/IntelRealSense/realsense-ros/releases),[moreInfo](https://github.com/IntelRealSense/realsense-ros/issues/395)
* ros_kinetic-realsense-camera (after installing the realsense ros wrapper)


## Installation
* clone
* catkin_make
* chmod +x -R ~/franka_python
* Note: if using pycharm (for it to recognize ROS pkgs: sudo chown -R <ur_usr> /usr/share/applications)
  

## Execution
* Terminal1 (ROS, Gazebo, moveIT!): `roslaunch franka_gazebo franka_gazebo.launch`
* Terminal2 (Python Control Node): `roslaunch franka_control franka_keyboard_control.launch`


## License

All packages of `franka_stack` (formerly `franka_ros`) are licensed under the [Apache 2.0 license][apache-2.0].

[apache-2.0]: https://www.apache.org/licenses/LICENSE-2.0.html
[fci-docs]: https://frankaemika.github.io/docs
[travis-status]: https://travis-ci.org/frankaemika/franka_ros.svg?branch=kinetic-devel
[travis]: https://travis-ci.org/frankaemika/franka_ros

**Based on the works of**
* Marcus Ebner von Eschenbach (sven-hoek) [git](https://github.com/sven-hoek/franka_ros) 
* Yuval Litvak [ref](https://arxiv.org/abs/1809.10699)
* Erdal Pekel [git](https://github.com/erdalpekel)
* Marko Križmančić [git](https://github.com/mkrizmancic) 
