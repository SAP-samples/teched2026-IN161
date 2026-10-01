# IN161 - Exercise 6 - Create a New Overlay Mapping

## Overview
In this exercise, you will create an overlay mapping, use it in Trading Partner Management, send a test message, and verify the result in the B2B Monitor.

Base and overlay mappings let you capture common logic once in a base MAG and then create lean overlay MAGs for each partner that only add, delete, or override differences. This reduces duplication and speeds up onboarding. Updates in the base MAG propagate to all overlays, improving consistency and maintainability. Overlay mappings also handle partner-specific variations (for example, date formats or additional fields) without rebuilding the entire mapping.

For more details, see this blog:
https://community.sap.com/t5/integration-blog-posts/base-overlay-mappings-for-integration-advisor/ba-p/14017329

----

![IN161-6_01](assets/IN161-6_1.png)
In the left-hand navigation, go to Design -> MAGs.

----

![IN161-6_02](assets/IN161-6_2.png)
Click Create -> Overlay MAG.

----

![IN161-6_03](assets/IN161-6_3.png)
Select the base MAG: _P2P-01 #BASE IDOC ORDRSP.ORDERS05-to-UN EDIFACT D.02A ORDRSP_.

----

![IN161-6_04](assets/IN161-6_4.png)
Select the base source MIG: _P2P-01 Bestrun-IDOC ORDRSP.ORDERS05-Source_.

----

![IN161-6_05](assets/IN161-6_5.png)
Select the overlay target MIG: _P2P-01 IN161-XX - UN-EDIFACT D.02A ORDRSP - Target_ (replace XX with your number).

----

![IN161-6_06](assets/IN161-6_6.png)
Enter Name: _P2P-01 IN161-XX SAP IDoc ORDRSP.ORDERS05-to-UN-EDIFACT D.02A ORDRSP_ (replace XX with your number), then click Create.

----

![IN161-6_07](assets/IN161-6_7.png)
When prompted with Update Constants, click _Update_.

----

![IN161-6_08](assets/IN161-6_8.png)
Set the filter to show _Only Errors_.

----

![IN161-6_09](assets/IN161-6_9.png)
For each erroneous mapping listed, click the Action (X) button on the right to remove it, until all are deleted.

----

![IN161-6_10](assets/IN161-6_10.png)
Now exclude one mapping from the base mapping, as it is not needed in our overlay.
In the source structure, search for E1EDP01->E1EDP01->PMENE, select the mapping line, and right-click to open the menu and delete that mapping.

----

![IN161-6_11](assets/IN161-6_11.png)
Because this excludes a mapping inherited from the base, confirm by selecting _Exclude Base Mapping_.

----

![IN161-6_12](assets/IN161-6_12.png)
For the remaining overlay mapping work, request a proposal from the knowledge base to save time. Click _Proposal_.

----

![IN161-6_13](assets/IN161-6_13.png)
Use only proposals that do not conflict with the base mapping. Select _Non-Conflicting Proposals_.

----

![IN161-6_14](assets/IN161-6_14.png)
To automatically apply the proposal with the highest confidence, click _Select Best Proposal_.

----

![IN161-6_15](assets/IN161-6_15.png)
Because the knowledge base can include mapping functions that may not work in your context, select _Use Only Valid Mappings_ to exclude non-working snippets.

----

![IN161-6_15a](assets/IN161-6_15a.png)
Please press _Clear Proposal_.

----
![IN161-6_16](assets/IN161-6_16.png)
Now _Save_ the mapping.

----

![IN161-6_20](assets/IN161-6_20.png)
In the left-hand navigation, go to B2B Scenarios -> Agreements.

----

![IN161-6_21](assets/IN161-6_21.png)
Open your agreement IN161-UserXX-copy (replace XX with your number). The agreement should be _Active_, as you activated it in the previous exercise.

----

![IN161-6_22](assets/IN161-6_22.png)
Switch to the B2B Scenarios tab of the agreement to replace the mapping with your new overlay MAG.

----

![IN161-6_23](assets/IN161-6_23.png)
Switch the B2B Scenario to _Edit_ mode.
In the Purchase Order Request Response transaction flow:
- Click the _Mapping_ box in the lower lane.
- In the details pane, click the _Mapping_ field to open the selection dialog.

----

![IN161-6_24](assets/IN161-6_24.png)
In the Select MAG dialog, search for IN161 and select:
_P2P-01 IN161-XX SAP IDoc ORDRSP.ORDERS05-to-UN-EDIFACT D.02A ORDRSP_ (replace XX with your number).
Click _Choose_.

----

![IN161-6_25](assets/IN161-6_25.png)
In the same transaction flow, click the _Interchange_ box next to the mapping you just replaced. You also need to update the MIG to your newly created overlay target MIG.
- In the details pane, scroll down to the _MIG_ selector and open the selection dialog.

----

![IN161-6_26](assets/IN161-6_26.png)
In the Select MIG dialog, search for IN161 and select the overlay target MIG:
_P2P-01 IN161-XX - UN-EDIFACT D.02A ORDRSP - Target_ (replace XX with your number).
Click _Choose_.

----

![IN161-6_27](assets/IN161-6_27.png)
Click _Save_ on the agreement, then click _Update_ to write the changes to the Partner Directory.

----

![IN161-6_28](assets/IN161-6_28.png)
Wait until the extraction of runtime data is complete and the agreement returns to _Active_.

----

![IN161-6_29](assets/IN161-6_29.png)
Send a test message:

In the left-hand navigation, go to Design -> Integrations and APIs -> IN161-UserXX (replace XX with your number).

----

![IN161-6_30](assets/IN161-6_30.png)
Open _Artifacts_.

----

![IN161-6_31](assets/IN161-6_31.png)
Click _More_ (...) -> _Deploy_.

----

![IN161-6_32](assets/IN161-6_32.png)
Wait for the deployment to finish. You should see a success message similar to:
IN161-Send EDIFACT Order UserXX successfully deployed.
Then go to Monitor -> B2B Scenarios.

----

![IN161-6_33](assets/IN161-6_33.png)
Open _Interchanges_.

----

![IN161-6_34](assets/IN161-6_34.png)
Find your outbound interchange and open it by selecting the row. Check the interchange status.

----

![IN161-6_35](assets/IN161-6_35.png)
Scroll down to the payload and review _Receiver Interchange Assembled_.
- Optionally, cross-check other key fields from the reference list above.

----

Continue with [Exercise 7 - Work with the Functional Acknowledgment](Exercise-7.md).

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
