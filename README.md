# ASL Jackal
Stuff to get up and running with the Jackal quickly.

## Initial Setup

(For your computer)

1. Clone this repository into a catkin workspace
2. `catkin_make` to compile the package
3. Add `source <workspace_name>/devel/setup.bash` to your `~/.bashrc`
4. Add `export $JACKAL_URDF_EXTRAS=<workspace_location>/src/asl_jackal/urdf/jackal_extension.urdf` to your `~/.bashrc`

(For the Jackal)

1. 

## Simulation

1. `roslaunch asl_jackal nav_world.launch`
2. `roslaunch jackal_viz view_robot.launch config:=navigation`

## Real Life

1. 