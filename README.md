# Automated-warehouse-robot_low-cost
A warehouse is a commercial building generally used for storage of goods and warehousing is the process of proper storage and handling of goods. Manual warehouses use manpower (forklift, human labor) for their operation. Dramatic rise in e-commerce has increased number of people ordering worldwide from 58% in 2014 now increased to 65% in 2020. The feasibility of human labor decreased due problems like human error and limited working hours and less efficiency. Industrial automation is the use of control systems, such as computers or robots, and information technologies for handling different processes and machineries in an industry to replace a human being. In long term use automation can reduce labor cost, man power and it also reduces accident due to human error. This project is intended to construct an autonomous forklift robot that use using Path Count to find the targeted storage slot and goods identification. Experimental results are given which show that the project is a useful robot for the purposes already mentioned.  
Keywords:  Line follower, Bluetooth, Warehouse, Motor Driver, Forklift 
Group Members- Amal Antony, Alen C Binu, Alen Sabu


# Methodology
# 1 Data Input
Every package is provided with unique number. The information of the package to be picked is given through Bluetooth module. The Bluetooth module communicate to the microcontroller through Arduino’s serial monitor.  
2 Line Follower
Robot is placed at starting location on the line. The system uses 5 IR sensor for the controlling of the robot. The robot is placed such that all sensors are on HIGH on white surface (white = HIGH). Robot turns right and places itself on the track such that middle sensor is on the line. The main path following is done using middle sensor. The robot follows a straight line as long as middle sensor on the black line (black = LOW). Motor driver drives motor forward as long as middle sensor is LOW and adjacent two are used for maintaining the path. When adjacent sensors enter black line the motor on that side stops to get back to the path. 
Each junction is provided with a cross-like pattern in order to identify the track number. Robot follows the path till it reaches the junction, once it reaches the junction all IR values are LOW. The path variable in the algorithm is incremented by 1. The microcontroller checks if the package information and path variable are equal, if not equal the path is followed by the robot till it reaches the next junction, again at reaching the next junction the path variable is incremented by 1. When package information matches with the path variable the robot turns to the right until the middle sensor aligns with the black line. The path is followed as the middle sensor LOW. Until it reaches package position.
3 Package Picking
As discussed in 3.2 the robot reaches the package location. The stopping location is identified using when bottom 4 IR sensors are LOW and the middle sensor is HIGH. The motor is stopped at this position in order to pick the package.
![image](https://user-images.githubusercontent.com/69912609/214695868-10dba072-ad13-413d-aa8b-7d64da87416f.png)
 
Initially the fork is in zero position. After stopping, the robot arm is automatically aligning itself underneath the package. The servo motor rotates from 0⁰ to 70⁰ to raise the package.
# 4 Return Mechanism
Once the package is picked the robot turns backward at this time no sensor values are on microcontroller controls the motor driver to turn the robot right. At this time the middle sensor aligns on black line and follows the path towards the starting position. 
![image](https://user-images.githubusercontent.com/69912609/214695827-d79cf857-a559-405d-8f80-9835d0550a9b.png)

In order to deliver the package, the position at which the motor has to be stooped is identified when the top middle sensor is LOW and outermost 2 IR sensors are HIGH. At the location the servo moves from 60⁰ to 0⁰ to lower the arm to place the package. Robot moves backward and process is reset itself and is ready for next package.
 
# 5 Simulation
WEBOTS application is used for simulation and modeling of warehouse robot. The figure 4.1 shows the overview of the robot where the robot is in its starting position. In figure 4.4 the packages are shown where it is placed in their specific location.
![image](https://user-images.githubusercontent.com/69912609/214695700-c29cadc0-1838-41bb-9361-8798c517c574.png)

![image](https://user-images.githubusercontent.com/69912609/214695621-df3694c3-1420-44f4-b9ae-71f53233bce0.png)

Prior to the development of final robot. Appropriate components are chosen and algorithm was developed and tested. Addition to that line follower algorithm was simulated using Webots software application.


# Prototype
# 1 Data Input
The robots start working when the input is given to the serial monitor. The Bluetooth       module is used to communicate with the mobile device. 
![image](https://user-images.githubusercontent.com/69912609/214697020-4355a433-b586-4425-bd73-cc3de577fdb3.png)
![image](https://user-images.githubusercontent.com/69912609/214697058-2b39924c-3711-4cbc-994a-a00a111b1783.png)

Figure 5.1 shows the data input method for picking the box from the starting point. After receiving the input robot moves to the package location. On reaching the specified track the track number is shown in the monitor as shown in figure 5.2

# 2 Hardware Implementation
![image](https://user-images.githubusercontent.com/69912609/214697216-361243c1-1240-4da5-a79e-d87c54872cc9.png)

![image](https://user-images.githubusercontent.com/69912609/214697255-bb2a52b3-45c0-4862-9f4b-c3eba8acb573.png)



