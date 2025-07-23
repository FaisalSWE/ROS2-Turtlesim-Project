# ROS 2 Turtlesim Project 

This project demonstrates how to use the `turtlesim` package in ROS 2 (Humble) with basic commands and manipulation using topics and services.

---

##  1. Create and Build Workspace

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
colcon build
source install/setup.bash
```

---

##  2. Run the turtlesim GUI

```bash
ros2 run turtlesim turtlesim_node
```

---

##  3. Control the turtle with keyboard

Open a second terminal:

```bash
ros2 run turtlesim turtle_teleop_key
```

---

##  4. Play with Topics

List all topics:

```bash
ros2 topic list
```

Echo pose:

```bash
ros2 topic echo /turtle1/pose
```

Move turtle manually:

```bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0}, angular: {z: 1.8}}"
```

---

##  5. Play with Services

List all services:

```bash
ros2 service list
```

Clear screen:

```bash
ros2 service call /clear std_srvs/srv/Empty
```

Spawn another turtle:

```bash
ros2 service call /spawn turtlesim/srv/Spawn "{x: 5.0, y: 5.0, theta: 0.0, name: 'turtle2'}"
```

