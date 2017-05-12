# ASL Jackal
Stuff to get up and running with the Jackal quickly.

## Initial Setup

(For your computer)

1. Clone this repository into the `src` directory of a catkin workspace
2. `catkin_make` to compile the package*
3. Add `source <workspace_name>/devel/setup.bash` to your `~/.bashrc`
4. Add `export JACKAL_URDF_EXTRAS=<workspace_location>/src/asl_jackal/urdf/jackal_extension.urdf` to your `~/.bashrc`

(For the Jackal)

1. Clone this repository into `~/catkin_ws/src/`
2. `catkin_make` to compile the package*
3. Add `export JACKAL_URDF_EXTRAS=/home/administrator/catkin_ws/src/asl_jackal/urdf/jackal_extension.urdf` to `/etc/ros/setup.bash`
4. Add `source /home/administrator/catkin_ws/devel/setup.bash` to `/etc/ros/setup.bash`
5. `sudo cp catkin_ws/src/asl_jackal/launch/move_base.launch /etc/ros/indigo/ros.d/`
6. Reboot

*(If the package doesn't build, it may help to delete existing `devel` and `build` folders in the workspace)

## Simulation

1. On your computer, run `roslaunch asl_jackal nav_world.launch`
2. On your computer, run `roslaunch jackal_viz view_robot.launch config:=navigation`

## Real Life

1. Get on the same network as the Jackal (MARK_AP_5G)
2. On your computer, `export ROS_MASTER_URI=http://128.84.189.147:11311`
3. On your computer, `export ROS_IP=<your ip address>`
4. On your computer, run `roslaunch jackal_viz view_robot.launch config:=navigation`

## Record and Playback

1. On your computer, examine the full list of topics that are currently being published. `rostopic list -v`
2. To begin recording, open a new terminal. The <-O> option tells rosbag record to only subscribe to the specified topics. 
`rosbag record -O <topics>`
3. Move the Jackal as desired using RViz.
4. To stop recording, hit Ctrl+C in the rosbag terminal window. 
5. To examine what was recorded in the bagfile, execute the following command from the directory in which the bagfile is stored. 
`rosbag info <bagfile>`

To playback in real life: 
6. `rosbag play <bagfile>`. The recording will playback in real life.

To playback in simulation:
6. Close RViz.
7. On your computer, comment out`export ROS_MASTER_URI=http://128.84.189.147:11311` and `export ROS_IP=<your ip address>` in your ./bashrc.
8. Launch Gazebo: `roslaunch jackal_viz view_robot.launch config:=navigation`
9. Launch RViz: `roslaunch jackal_viz view_robot.launch config:=navigation`
10. To playback the bag file, `rosbag play <bagfile>`. The respective recording will now play back in simulation.

For more information, see http://cornell-asl.org/index.php?title=Simulating_the_Jackal.



