# IN161 - Exercise 6 - Create your own Mapping Guideline (MAG) using proposals

## Overview
**Prerequisite**:   
Downlaod the Source payload for the simulation Steps [IDoc_Sample_Payload](Payload/IDoc_Sample_Payload.txt)<br>


Until now, your agreement has used the mapping that was **migrated from PI/PO** and was already available in the tenant. That is the fastest way to go live, but you often want to own and evolve the mapping yourself in Integration Advisor.

In this exercise you will create your **own Mapping Guideline (MAG)** that maps the SAP IDoc **ZQMOUTTC** (quality certificate) to **ANSI X12 863** (Report of Test Results, version 004010). Instead of mapping every field by hand, you will let the Integration Advisor **knowledge base propose** the mapping for you. Finally, you will plug your new MAG into your Copy agreement, send a message, and verify the result in the B2B Monitor.

The source and target Message Implementation Guidelines (MIGs) already exist in the tenant:
- Source MIG: _[IN161] Ironvale Steel Corp. - IDoc - Source_
- Target MIG: _[IN161] Heartland Metals Supply Co. - 863 - Target_

As usual, replace XXX with your participant number wherever it appears.

> Note: The exact MIG/MAG names above are tenant-specific – please verify them against your tenant.
> In case you face issues executing the Mapping steps you can create a new mapping guideline by copying an existing mapping guideline "Mapping [IN161] Ironvale Steel Corp. - IDoc - Source to [IN161] Heartland Metals Supply Co. - 863 - Target" 
 Follow the steps: 
    1) In the Mapping Guidelines tab, select  More Options next to the MAG that you want to copy and choose Copy.
    2) Then, choose the following copy option:
        a) Copy  Copy MAG Only: This option creates only a copy of the MAG, reusing the MIGs from the copied MAG.
        A new copy of the mapping guidelines opens, and you can work with it right away.

----
In the left-hand navigation, go to Design -> MAGs.
![Open MAGs](assets/exercise6/IN161_6_01.png)<br>



----
Click Create -> Graphical MAG:Standard.
![Create MAG](assets/exercise6/IN161_6_02.png)



----
Select the source MIG: [IN161] Ironvale Steel Corp. - IDoc - Source
![Select source MIG](assets/exercise6/IN161_6_03.png)


----
Select the target MIG: [IN161] Heartland Metals Supply Co. - 863 - Target
![Select target MIG](assets/exercise6/IN161_6_04.png)


----
Enter the MAG name using the following naming scheme: Mapping [IN161] UserXXX IDoc - Source to 863 - Target (replace XXX with your number), then click Create.
![Name the MAG](assets/exercise6/IN161_6_05.png)


----
Your new MAG opens in the mapping editor. It is still empty – no fields are mapped yet. This activity applies to finding the corresponding source and target nodes that are semantically equivalent and creating complex functions if the values cannot be copied from the source side to the target side.<br> 
To accelerate the mapping of the source to target elements and avoid mapping everything manually, request a proposal from the knowledge base: click Propose in the upper-right corner next to the Simulate button. Depending on the number of good-quality contributions for the specific message types, this  provides a corresponding proposal of possible mapping elements. This proposal will be a starting point for  finalization in this overall exercise.
![Request a proposal](assets/exercise6/IN161_6_06.png)<br>


----
To automatically apply the proposal with the highest confidence, click Select Best Proposal in the Details section at the lower part of the screen, next to the Validate button.
![Select Best Proposal](assets/exercise6/IN161_6_07.png)<br>



----
Because the knowledge base can include mapping functions that may not work in your context, click Validate in the Details section to ensure only valid mapping elements/function snippets are used.
![Use only valid mappings](assets/exercise6/IN161_6_08.png)<br>



----
Review the proposed mappings. The knowledge base maps the quality-relevant fields (for example, inspection/test values and their units) from the ZQMOUTTC structure to the corresponding ANSI X12 863 segments. Then click Save.
![Review and Save](assets/exercise6/IN161_6_09.png)<br>



----
Now use your new MAG in your agreement. Go to B2B Scenarios in the left-hand navigation under Design and go to -> Agreements and open your agreement Quality Certificate-UserXXX. It should be Active from the previous exercise.
![Open your agreement](assets/exercise6/IN161_6_10.png)


----
Switch to the B2B Scenarios tab and set the B2B Scenario to Edit mode. In the QualityCertificate_Outbound transaction flow:
- Click the Mapping box.
- In the details pane, click the Mapping field to open the selection dialog.
- Search for your MAG Mapping [IN161] UserXXX IDoc - Source to 863 - Target and select it, then click Choose. If you do not find your MAG, click Reset to see all the available MAGs from Integration Advisor.
![Replace the mapping with your MAG](assets/exercise6/IN161_6_11.png)<br>



----
Click Save on the agreement, then click Update to write the changes to the Partner Directory. Wait until the agreement returns to Active.
![Save and Update the agreement](assets/exercise6/IN161_6_12.png)<br>



----
Send a test message: go to Design -> Integrations and APIs -> IN161-UserXXX, open Artifacts, click the three dots (...) -> Deploy. Then go to Monitor -> B2B Scenarios -> Interchanges, click Go, and open your outbound interchange to confirm the ANSI X12 863 message was produced by your own MAG.
![Send a test message and verify](assets/exercise6/IN161_6_13.png)<br>



----

Continue with: [Exercise 7 - Enhance the mapping with Joule](Exercise-7.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
