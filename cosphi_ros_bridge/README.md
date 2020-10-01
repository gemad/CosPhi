
what is this node? 
-----------------------------------
-The purpose of this node is to integrate the CosPhi localization module into the ROS environment 
-The node will listen to the TCP Socket 6666 -which used by the CosPhi- to publish the result of the localization and parse it then publish ROS topic for each robot with Pose2D standard geometry msgs


Setup and Running :
-----------------------------------
1) add the folder CosPhi_ros_bridge to "catkin_ws/src" or your workspace/src
2)run $catkin_make to consider the new files 
3)run the main program as illustrated in the main tutorial of CosPhi
4)run the roscore node by using command $roscore
4)run the bridge by using command  
$rosrun CosPhi_ros_bridge CosPhi_ros_bridge_node.py
5)type $rostopic list
 you will find a topic for each robot detected


Test the output :
-----------------------------------
To see the output run this command 
$rostopic echo /cosphi_ros_bridge/robotXXX 
where XXX is the robot ID 

now let each robot subscribe for it's position t of the node on the topic 


you can  listen to the old output on this topic
$rostopic echo /cosphi_ros_bridge/poses 



error and solution :
-----------------------------------
if this error appears  just try to run the node again

"Traceback (most recent call last):
  File "~/catkin_ws/src/cosphi_ros_bridge/scripts/cosphi_ros_bridge_node.py", line 49, in <module>
    main()   
  File "~/catkin_ws/src/cosphi_ros_bridge/scripts/cosphi_ros_bridge_node.py", line 32, in main
    X = float(Array_All[2])
ValueError: could not convert string to float: of
"






