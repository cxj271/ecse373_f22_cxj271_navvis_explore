# ecse373_f22_cxj271_navvis_explore
ROS package for the navvis robot wandering around the 5th floor of Glennan

This package is dependent on the navvis_description ROS package:
https://github.com/cxj271/ecse373_f22_cxj271_navvis_description 


**How to run this ROS package:** 

roslaunch navvis_explore navvis_explore.launch

The launch file has an include for a launch file, navvis.launch, which is in a different package. 
For full explanation of the launch file navvis.launch, please see:
https://github.com/cxj271/ecse373_f22_cxj271_navvis_description 


**Additional Arguments:**
1. use_new_robot:= true/false
  - default = true
  - if true: uses the xacro file in the current project package to make the navvis robot (navvis_description ROSpackage) and adds an imu part
  - if false: does not use the new xacro, goes to the defaults in the navvis_description ROS package


2. bag_file_location:= "filepath"
  - should be the full filepath to the bag file
  - default = "$(find navvis_explore)/bag/glennan_5_complete.bag"


3. config_file_name:= "filename"
  - should be the filename of the config file for rviz including the file type extention
  - Three options: 
    1. config.rviz
      - basic .rviz config file
      - does not include the additions of the Laserscans or the Map
    2. config_w_laser_nomap.rviz
      - this configuration file includes the Laserscans in but not the Map
      - if use_new_robot = "true":
        - Shows the lasers but user will need to change the fixed frame and the target frame to show the map
      - if use_new_robot = "false"
        - Shows the "Laserscan" in the display panel but lasers cannot be seen in the visual panel
    3. config_w_map.rviz
      - **CANNOT BE USED IF use_new_robot = "false"**
      - Includes both the Laserscan and the Map. changes the fixed and target frames to be the map

**For more additional arguments, please visit the link to the navvis_description ROS package.**
