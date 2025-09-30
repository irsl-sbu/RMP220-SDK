# RMP220-SDK ROS Wrapper

## Building the ROS package

```
cd RMP220-SDK/ROS
catkin_make -DCATKIN_WHITELIST_PACKAGES='sgway_msgs'
catkin_make -DCATKIN_WHITELIST_PACKAGES='segwayrmp'
```

## Chassis Respose Test

(1) Turn off the remote control and ensure that the emergency stop button on the robot is not engaged

(2) Run the following command in three different terminals

```
cd RMP220-SDK/ROS
roscore
```

```
cd RMP220-SDK/ROS
source devel/setup.bash
rosrun segwayrmp SmartCar
```

```
cd RMP220-SDK/ROS
source devel/setup.bash
rosrun segwayrmp ChassisResponseTest
```

## ROS Package Description

- `segway_msgs` : Segway Messages Package
  - `segway_msgs/msg`   : Definitions of custom messages for RMP220
- `segwayrmp`   : Segway RMP Control Nodes
  - `segwayrmp/include` : Directory containing header files requried for control nodes
  - `segwayrmp/src`     : Segway RMP control nodes
  - `segwayrmp/tools`   : `ChassisResponseTest node` for testing robot

## Serial Port Settings for `ChassisResponseTest`

The ROS Parameter `segwaySmartCarSerial` is used to set the serial port that the robot is connected to

The default serial port set in `ChassisResponseTest.cpp` is `ttyUSB0`

```
n_.setParam("segwaySmartCarSerial", "ttyUSB0");
```

The serial port can be modified as needed
