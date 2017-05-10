# ASL Jackal
Stuff to get up and running with the Jackal quickly.

## Initial Setup

(For your computer)

1. Clone this repository into the `src` directory of a catkin workspace
2. `catkin_make` to compile the package
3. Add `source <workspace_name>/devel/setup.bash` to your `~/.bashrc`
4. Add `export $JACKAL_URDF_EXTRAS=<workspace_location>/src/asl_jackal/urdf/jackal_extension.urdf` to your `~/.bashrc`

(For the Jackal)

1. Clone this repository into `~/catkin_ws/src/`
2. `catkin_make` to compile the package
3. Add `export $JACKAL_URDF_EXTRAS=/home/administrator/catkin_ws/src/asl_jackal/urdf/jackal_extension.urdf` to your `~/.bashrc`
4. `sudo cp catkin_ws/src/asl_jackal/launch/move_base.launch /etc/ros/indigo/ros.d/`
5. Reboot

## Simulation

1. On your computer, run `roslaunch asl_jackal nav_world.launch`
2. On your computer, run `roslaunch jackal_viz view_robot.launch config:=navigation`

## Real Life

1. Get on the same network as the Jackal (MARK_AP_5G)
2. On your computer, `export ROS_MASTER_URI=http://128.84.189.147:11311`
3. On your computer, `export ROS_IP=<your ip address>`
4. On your computer, run `roslaunch jackal_viz view_robot.launch config:=navigation`

## Record and Playback