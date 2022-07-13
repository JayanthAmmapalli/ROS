# ROS
My path to learning ROS
Writing a Publisher
    • Create project folder
        ◦ $ mkdir catkin_ws
        ◦ $ mkdir src
        ◦ $ catkin_make – to compile the folder
    • Create the ROS package
        ◦ $ cd src
        ◦ $ catkin_create_pkg Package_name Dependencies
        ◦ Create a new folder in package called “scripts”
        ◦ No write a python node in that folder
    • Writing a node in Python
    • First import required packages and write a main part of code
        ◦ >> #!/usr/bin/env – tells to execute the file as python file
        ◦ >> import rospy
        ◦ >> from std_msgs.msg import String(or Float64)
        ◦ Create the main function
        ◦ >> if __name==’__main’:
        ◦ >>	try:
        ◦ >>		talk_to_me() - 
        ◦ executeting the function in which we write the code
        ◦ Now we write an exception
        ◦ >>	except rospy.ROSInterruptException:
        ◦ >>		pass
    • second we create the function
    • >> def talk_to_me():
    • >>	pub= rospy.Publisher(‘Name_of_topic’, ‘type_of_message(EG:String)’,queue_size=10)
    • Next we need to initialize the node
    • >>	rospy.init_node(‘Name_of_node’, anonymous=True)
    • anonymous=True means- if we have two nodes with same name, it will automatically create a new name for other node
    • now we set message rate(in Hz)
    • >>	rate=rospy.Rate(1)
    • >>	while not rospy.is_shutdown():
    • >>		msg = “Hello Jayanth - %s” % rospy.get_time()
    • Now we will publish this message
    • >>		pub.publish(msg)
    • >>		rate.sleep()





Creating a custom messages
    • Create a folder in package you are working in called “msg”
    • create a message file in that using fallowing command:
$ cat > msg/math.msg
    • After this type the message format in terminal and press ctr+D
    • In package.xml uncomment these two lines of code:
      <build_depend>message_generation</build_depend>
  	<exec_depend>message_runtime</exec_depend>
    • 
