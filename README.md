# Experiment-02-Introduction-to-Roboanalyzer-
## AIM: 
To Design & simulate an environment for pick & place operations with Industrial Robot using Robo DK software
### COMPONENTS REQUIRED:
1.	RoboDK

### THEORY: 

 Types of pick and place robots
There are several pick and place robot types and components, including:

Robotic arm – Robotic arms are the most common type of pick and place robots. A 5-axis robotic arm robot can be used for standard pick and place applications where objects are picked up and moved to other locations in a single plane. A 6-axis robotic arm robot is used for more complex applications, such as when objects must be twisted or re-oriented before being placed in another location.
Cartesian – Like a 6-axis robotic arm, Cartesian robots work in multiple planes. These robots move in three orthogonal axes (X, Y and Z) using Cartesian coordinates. They can be constructed with any type of linear actuator and several types of drive mechanisms such as belt, ball or lead screw mechanisms. They typically have better positioning accuracy compared to 6-axis robotic arms.
Delta – Often used in applications where robots pick items in groups and place them in assembly patterns or containers, Delta robots have advanced vision technologies that enable them to distinguish various sizes, shapes and colors. There are several configurations of Delta robots, but most have three arms that operate on four axes. They have heavy motors affixed to a frame, with lightweight arms connected to linking rods with joints at either end of each arm (typically ball joints) to allow movement.
Fast pick – Fast pick robots are ideal for use in medium- and high-volume applications with high-velocity SKUs. Fast pick robots fully automate the picking process, freeing up the human workforce to focus on higher-impact activities. They’re ideal for fast-moving “top-off” items, such as promotional items added to orders or batteries. These robots can pick up to 300 SKUs per hour from a pool of up to 8 SKUs.
Collaborative – Collaborative robots augment the work of humans by leading associates to pick locations and guiding associates through each task. By optimizing routes in real-time and keeping associates on task, collaborative robots help associates work more efficiently.

Applications for pick and place robots
Pick and place robots are often used in manufacturing but are also used in applications such as packaging, bin picking and inspection. Here’s a look at a few of the most common applications for pick and place robots and how they’re used.

Assembly – Pick and place robots used in assembly applications grab incoming parts from one location, such as a conveyor, and place or affix the part on another piece of the item. The two joined parts are then transported to the next assembly area.
Packaging – Pick and place robots used in the packaging process grab items from an incoming source or designated area and place the items in a packaging container.
Bin picking – Pick and place robots used in bin picking applications grab parts or items from bins. These pick and place robots typically have advanced vision systems allowing them to distinguish color, shape and size to pick the right items even from bins containing randomly mixed items. These parts or items are then sent to another location for assembly or packaging.
Inspection – Pick and place robots used for inspection applications are equipped with advanced vision systems to pick up objects, detect anomalies and remove defective parts or items by placing them in a designated location.


### PROCEDURE:


Select a robot New robots can be added from a local drive or from the online library:

Select File Open online library (Ctrl+Shift+O). A new nested window will appear showing the online library It is also possible to select the corresponding button in the toolbar. Use the filters to find your robot by brand, payload, ... In this example, we will use a UR10 robot (10 kg payload robot and 1.3 m reach). Select Download. The robot should automatically appear in the station in a few seconds. The online library can be closed once the robot is loaded Tip: Selecting reset filter in the online library will remove any filter that was use Tip: Alternatively, it is also possible to download the robot files (.robot extension) separately, from the website: http://robodk.com/library and open them in RoboDK by drag & dropping the file to the main window or by selecting FileOpen. Note: Every time a new robot is loaded in RoboDK, a new reference frame is added representing the robot base frame. Note: Loading robots from the online library will store them in the local library. The default location of this folder is: C:/RoboDK/Library/.

Add a Reference Frame A Reference frame allows placing objects with respect to a robot or with respect to other objects in the 3D space (including position and orientation). Note: More information about reference frames in RoboDK in the reference frames section. To add a new reference frame:

Select Program Add Reference Frame Alternatively, select the equivalent button in the toolbar Double click the reference frame (on the tree or on the 3D geometry on the main screen) to enter the coordinates shown in the image (X,Y,Z position and Euler angles for the orientation). The mouse wheel can be used on top of each case to quickly update the position of the reference frame on the main screen. The following colors are used by default: o X coordinate Red o Y coordinate Green o Z coordinate Blue o 1st Euler rotation Cyan o 2nd Euler rotation Magenta o 3rd Euler rotation Yellow Tip: Select Tools>Options>Display>Display XYZ axis letters to see the Coordinate system axes. Select ViewMake reference frames bigger (+) to increase the size of the reference frames Select ViewMake reference frames smaller (-) to decrease the size of the reference frames Select ViewShow/Hide text on screen (/) to show or hide the text on the screen Optionally, rename any reference frame or object in the tree by selecting F2
	 



### PROGRAM 
```
NAME:Karthick raj M
reg:212221040073
```


```
PICKANDPLACE()

# RoboDK Python Intermediate file to generate robot programs.
# Program name: PICKANDPLACE
# This file requires the post processor: 
#   Doosan_Robotics
# to generate your robot program.
# This is a temporary file and you can delete it once you have generated your program.
# 
# Post processor documentation: https://robodk.com/doc/en/PythonAPI/postprocessor.html

import sys
import os
sys.path.append(os.path.abspath(r"""D:\RoboDK\Posts""")) # temporarily add path to POSTS folder

from Doosan_Robotics import *

try:
from robodk.robomath import PosePP as p
except:
# This will be removed in future versions of RoboDK
from robodk import PosePP as p


print('Total instructions: 5')
r = RobotPost(r"""Doosan_Robotics""",r"""Doosan Robotics M1013""",6, axes_type=['R','R','R','R','R','R'], ip_com=r"""127.0.0.1""", api_port=20500, prog_ptr=1714675767904, robot_ptr=1714846103984)

r.ProgStart(r"""PICKANDPLACE""")
r.RunMessage(r"""Program generated by RoboDK v5.4.1 for Doosan Robotics M1013 on 15/06/2022 09:17:19""",True)
r.RunMessage(r"""Using nominal kinematics.""",True)
r.setFrame(p(-488.144,228.25,-8.35768,0,0,0),-1,r"""objects frame""")
r.setTool(p(0,0,130,0,0,0),85,r"""Gripper RobotiQ 85 Opened""")
r.MoveJ(p(28.6354,21.5025,59.9813,176.39,3.37362,179.787),[-24.0788,-17.8977,-124.071,-2.09565,-41.1372,-18.8596],[0,0,0])
r.MoveJ(p(30.3743,21.5025,30.5417,176.39,3.37362,179.787),[-24.1551,-20.4588,-125.034,-2.26563,-37.6141,-18.7192],[0,0,0])
r.RunMessage(r"""Attach to Gripper RobotiQ 85 Opened""",True)
r.MoveJ(p(2.62017,21.5025,500.424,176.39,3.37362,179.787),[-22.9898,0.00657528,-93.0696,-1.31959,-90.0493,-19.3516],[0,0,0])
r.MoveJ(p(3.71469,-430.862,500.489,-179.861,3.3803,-179.992),[25.7617,1.8996,-94.9211,1.46849,-90.0235,25.5844],[0,0,0])
r.MoveJ(p(30.2054,-430.862,51.997,-179.861,3.3803,-179.992),[27.0464,-17.1299,-126.619,2.4267,-39.2881,24.9885],[0,0,0])
r.RunMessage(r"""Detach from Gripper RobotiQ 85 Opened""",True)
r.ProgFinish(r"""PICKANDPLACE""")
r.ProgSave(r"""C:/Users/LokiUday/OneDrive/Documents/RoboDK""",r"""PICKANDPLACE""",True,r"""C:/Users/LokiUday/Downloads/apps/RoboDK/Other/VSCodium/VSCodium.exe""")

```
### SIMULATION:


 
 
 ![image](https://github.com/KARTHICKRAJM84/Experiment-02--Design-simulate-an-environment-for-pick-place-operations-with-Industrial-Robot-us/assets/128134963/cfcfcfe2-b850-4975-83ef-f841e7005028)

 
 
 ![image](https://github.com/KARTHICKRAJM84/Experiment-02--Design-simulate-an-environment-for-pick-place-operations-with-Industrial-Robot-us/assets/128134963/f1fc5f2a-e133-44ba-a18f-f9ee8591328f)

 
![image](https://github.com/KARTHICKRAJM84/Experiment-02--Design-simulate-an-environment-for-pick-place-operations-with-Industrial-Robot-us/assets/128134963/34101193-4dfe-4097-886f-96ae216e3db6)
 
 
 
 
 ![image](https://github.com/KARTHICKRAJM84/Experiment-02--Design-simulate-an-environment-for-pick-place-operations-with-Industrial-Robot-us/assets/128134963/9ee717bd-9c8c-447c-8a82-5adcd7e0f406)

 
 
 
 
 
 
![image](https://github.com/KARTHICKRAJM84/Experiment-02--Design-simulate-an-environment-for-pick-place-operations-with-Industrial-Robot-us/assets/128134963/9d8993ff-2052-4baa-a7ff-1fd8a3e5571a)















### RESULTS :  

Thus, an environment for pick & place operations with Industrial Robot using Robo DK software is designed and simulated.
