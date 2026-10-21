# IN161 - Exercise 5 — (Optional) Create Target Message Implementation Guideline(MIG)

## Overview
In this exercise you will create the Trading Partner specific Target MIG.  
Prerequisite: Payload _XYZ X12 863.edi_ (download from the Payload Folder)  
Goto Message Implmenentation Guidelines Overview screen, Select in the Create button dropdown the "Create by Payload" option. ![IN161-5_01](assets/exercise5/IN161-7_01.png) 
Drop in or select the prepared Payload and navigate through the guided steps by confirming the proposed selection for the X12 Type System, 863 Message, with the selected Version of 004010 . 
![IN161-7_02](assets/exercise5/IN161-7_02.png)
![IN161-7_03](assets/exercise5/IN161-7_03.png) 
![IN161-7_04](assets/exercise5/IN161-7_04.png)

Select Envelope, and navigate to the "Sample Payload" selection Step.
![IN161-7_05](assets/exercise5/IN161-7_05.png) 

Select all offered options inlcuding "Set Example Values" as indicated by the Screenshot
![IN161-7_06](assets/exercise5/IN161-7_06.png) 

Go to the Qualification step and select the nodes as indicated by the Screenshot
![IN161-7_07](assets/exercise5/IN161-7_07.png) 

Hit the Create button on the lower right corner. The MIG Creation Dialog opens where you need to specify the Name and Direction of the MIG as well the Business Context Information. 
Specify: 
 	MIG Name: "UserXXX - 863 - Target MIG (replace XXX with your number) 
 	Direction : Out 
Own Business Context: Select Country Germany ( 1 would be enough...) 
![IN161-7_08](assets/exercise5/IN161-7_08.png) 


Navigate the the Second Tab called "Structure" and select the "Get Proposal" button from the right upper corner. 
 ![IN161-7_09](assets/exercise5/IN161-7_09.png) 

In the Structure you will see a new Column called "Confidence" with blue bars and beside selected Nodes like **ST** under **863** selection button 
Navigate to the node **ST** select the two boxes action and select the proposed Qualification Value _863_ to qualify the **ST** Segement from the Element **143** _Transaction Set Identifier Code_. This qualification is constant value which will be automatically taken over at the Mapping Excercise.
  ![IN161-7_10](assets/exercise5/IN161-7_10.png) 

Congratulations — you have finished the TechEd exercise!

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
