# roch_rapps Of Roch Stack Package


## Table of Contents
* [Preparation](#preparation)
* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)

## Preparation

Before starting run roch_rapps. There have some problems should be resolved, due to new packages of robotics-in-concert have not release with almost version in 0.10.0, so we should install these by ourselves.

### Requirements

Under these stacks packages we need, and corresponding version:

Stacks & Packages | Version | Document |
---------------- | ----------------- | ------------------|
**capabilities** | 0.2.0 & above | [wiki](https://wiki.ros.org/capabilities) [github](https://github.com/osrf/capabilities) |
**rocon_rapps** | 0.1.0 & above | [wiki](https://wiki.ros.org/rocon_rapps) [github](https://github.com/robotics-in-concert/rocon_rapps) |
**concert_scheduling** | 0.7.0 & above | [wiki](https://wiki.ros.org/concert_sceduling) [github](https://github.com/utexas-bwi/concert_scheduling) |
**concert_services** | 0.1.12 & above | [wiki](https://wiki.ros.org/concert_services) [github](https://github.com/robotics-in-concert/concert_services) |
**concert_software_farm** | 0.0.3 & above | [wiki](https://wiki.ros.org/concert_software_farm) [github](https://github.com/robotics-in-concert/rocon_concert) |
**rocon_app_platform** | 0.10.0 & above | [wiki](https://wiki.ros.org/rocon_app_platform) [github](https://github.com/robotics-in-concert/rocon_app_platform) |
**rocon_concert** | 0.9.0 & above | [wiki](https://wiki.ros.org/rocon_concert) [github](https://github.com/robotics-in-concert/rocon_concert) |
**rocon_msgs** | 0.10.0 & above | [wiki](https://wiki.ros.org/rocon_msgs) [github](https://github.com/robotics-in-concert/rocon_msgs) |
**rocon_multimaster** | 0.7.10 & above | [wiki](https://wiki.ros.org/rocon_multimaster) [github](https://github.com/robotics-in-concert/rocon_multimaster) |
**rocon_qt_gui** | 0.9.0 & above | [wiki](http://wiki.ros.org/rocon_qt_gui) [github](https://github.com/robotics-in-concert/rocon_qt_gui) |
**rocon_qt_library** | 0.9.0 & above | [wiki](http://wiki.ros.org/rocon_qt_library) [github](https://github.com/robotics-in-concert/rocon_qt_gui) |
**rocon_tools** | 0.6.0 & above | [wiki](http://wiki.ros.org/rocon_tools) [github](https://github.com/robotics-in-concert/rocon_tools) |
**rqt_capabilities** | 0.1.2 & above | [wiki](http://wiki.ros.org/rqt_capabilities) [github](https://github.com/osrf/rqt_capabilities) |
**std_capabilities** | 0.0.0 |  [github](https://github.com/osrf/std_capabilities) |
**world_canvas_server** | 0.1.0 | [wiki](http://wiki.ros.org/world_canvas_server) [github](https://github.com/corot/world_canvas) |
**world_canvas_libs** | 0.1.0 | [github](https://github.com/corot/world_canvas_libs) |
**world_canvas_msgs** | 0.1.0 | [wiki](http://wiki.ros.org/world_canvas_msgs) [github](https://github.com/corot/world_canvas_msgs) |

Add some packages we can using `````apt-get````` for installing following command:
```
$  sudo apt-get install ros-indigo-world-canvas-server ros-indigo-world-canvas-client-cpp \
    ros-indigo-world-canvas-client-examples ros-indigo-world-canvas-client-py ros-indigo-world-canvas-utils \
    ros-indigo-world-canvas-msgs ros-indigo-std-capabilities ros-indigo-rqt-capabilities \
    ros-indigo-concert-software-farm ros-indigo-capabilities ros-indigo-concert-services  \
    ros-indigo-concert-scheduling 
```
### Installation

Under these stacks packages we need to install by ourselves:

Stacks & Packages | version |
------------------- | ------------------- |
[rocon_app_platform](https://github.com/robotics-in-concert/rocon_app_platform) | 0.10.0 & above |
[rocon_concert](https://github.com/robotics-in-concert/rocon_concert) | 0.10.0 & above |
[rocon_msgs](https://github.com/robotics-in-concert/rocon_msgs) | 0.10.0 & above |
[rocon_qt_gui](https://github.com/robotics-in-concert/rocon_qt_gui) | 0.9.0 & above |
[rocon_qt_library](https://github.com/robotics-in-concert/rocon_qt_library) | 0.9.0 & above |
[rocon_tools](https://github.com/robotics-in-concert/rocon_tools) | 0.6.0 & above |

Download these packages into your workspace:
```
$  cd  <your_catkin_ws>/src
$  git clone https://github.com/robotics-in-concert/rocon_app_platform
$  git clone https://github.com/robotics-in-concert/rocon_concert
$  git clone https://github.com/robotics-in-concert/rocon_msgs
$  git clone https://github.com/robotics-in-concert/rocon_qt_gui
$  git clone https://github.com/robotics-in-concert/rocon_tools
$  git clone https://github.com/robotics-in-concert/rocon_multimaster
```
After download these packages, build your ```catkin_ws```:
```
$  cd  <your_catkin_ws>
$  #checkout all required depends installation
$  rosdep install --from-paths src --ignore-src --rosdistro indigo -y 
$  catkin_make
```
For now you can run ```concert_minimal.launch``` for using rapps of roch.

### Usage
There is an example for how to use roch_rapps, for now roch_rapps package is differebt old rocon package, due use new package, so you can use following command for checking.

 * `` (#For first ternimal)`` Bringup your Roch
 
   * ```  roslaunch roch_bringup concert_minimal.launch ```

 * `` (#For sencond ternimal)`` Bringup rqt_remocon
  
   * ``` rqt_remocon```
