# 5-DOF Robotic Arm (ROS Noetic + RViz)

Simulation and visualization of a 5-DOF robotic arm. The arm is described in URDF with five revolute joints, and the Joint State Publisher GUI moves each joint with a slider while RViz shows the links and TF frames.

## Requirements

- Ubuntu 20.04, ROS Noetic
- `ros-noetic-joint-state-publisher-gui`, `ros-noetic-robot-state-publisher`, `ros-noetic-rviz`

## Package structure

```
robotic_arm_5dof/
├── CMakeLists.txt
├── package.xml
├── urdf/     robotic_arm.urdf
├── launch/   display.launch
└── rviz/     robotic_arm.rviz
```

## Joints

| Joint | Type | Function |
|---|---|---|
| joint1 | Revolute | Base rotation |
| joint2 | Revolute | Shoulder movement |
| joint3 | Revolute | Elbow movement |
| joint4 | Revolute | Wrist movement |
| joint5 | Revolute | End-effector / wrist orientation |

## Build

```
cd ~/arm_ws
catkin_make
source devel/setup.bash
```

## Run

```
roslaunch robotic_arm_5dof display.launch
```

In RViz, set **Fixed Frame** to `base_link`, then add **RobotModel** and **TF**. Or load the saved layout with **File → Open Config** and choose `rviz/robotic_arm.rviz`. Move the sliders in the Joint State Publisher window to change the joint positions.
