# IN161 - Exercise 5 - Create your own Mapping Guideline (MAG) using proposals

## Overview
Until now, your agreement has used the mapping that was **migrated from PI/PO** and was already available in the tenant. That is the fastest way to go live, but you often want to own and evolve the mapping yourself in Integration Advisor.

In this exercise you will create your **own Mapping Guideline (MAG)** that maps the SAP IDoc **ZQMOUTTC** (quality certificate) to the **ANSI X12 863** (Report of Test Results). Instead of mapping every field by hand, you will let the Integration Advisor **knowledge base propose** the mapping for you. Finally, you will plug your new MAG into your Copy agreement, send a message, and verify the result in the B2B Monitor.

The source and target Message Implementation Guidelines (MIGs) already exist in the tenant:
- Source MIG: _QM-863 SAP IDoc ZQMOUTTC - Source_
- Target MIG: _QM-863 ANSI X12 004010 863 - Target_

As usual, replace XX with your participant number wherever it appears.

----

![IN161-5_01](assets/IN161-5_01.png)
In the left-hand navigation, go to Design -> MAGs.

----

![IN161-5_02](assets/IN161-5_02.png)
Click Create -> MAG.

----

![IN161-5_03](assets/IN161-5_03.png)
Select the source MIG: _QM-863 SAP IDoc ZQMOUTTC - Source_.

----

![IN161-5_04](assets/IN161-5_04.png)
Select the target MIG: _QM-863 ANSI X12 004010 863 - Target_.

----

![IN161-5_05](assets/IN161-5_05.png)
Enter the MAG name using the following naming scheme: _QM-863 IN161-XX ZQMOUTTC-to-ANSI X12 004010 863_ (replace XX with your number), then click Create.

----

![IN161-5_06](assets/IN161-5_06.png)
Your new MAG opens in the mapping editor. It is still empty – no fields are mapped yet. To avoid mapping everything manually, request a proposal from the knowledge base: click _Proposal_.

----

![IN161-5_07](assets/IN161-5_07.png)
To automatically apply the proposal with the highest confidence, click _Select Best Proposal_.

----

![IN161-5_08](assets/IN161-5_08.png)
Because the knowledge base can include mapping functions that may not work in your context, select _Use Only Valid Mappings_ to exclude non-working snippets.

----

![IN161-5_09](assets/IN161-5_09.png)
Review the proposed mappings. The knowledge base maps the quality-relevant fields (for example, inspection/test values and their units) from the ZQMOUTTC structure to the corresponding X12 863 segments. Then click _Save_.

----

![IN161-5_10](assets/IN161-5_10.png)
You should see a success message confirming that your MAG has been created and saved.

----

Now use your new MAG in your agreement.

![IN161-5_11](assets/IN161-5_11.png)
In the left-hand navigation, go to B2B Scenarios -> Agreements. Open your agreement IN161-UserXX-copy (replace XX with your number). It should be _Active_ from the previous exercise.

----

![IN161-5_12](assets/IN161-5_12.png)
Switch to the B2B Scenarios tab and set the B2B Scenario to _Edit_ mode. In the Report of Test Results transaction flow:
- Click the _Mapping_ box.
- In the details pane, click the _Mapping_ field to open the selection dialog.
- Search for IN161 and select your MAG: _QM-863 IN161-XX ZQMOUTTC-to-ANSI X12 004010 863_ (replace XX with your number), then click _Choose_.

----

![IN161-5_13](assets/IN161-5_13.png)
Click _Save_ on the agreement, then click _Update_ to write the changes to the Partner Directory. Wait until the extraction of runtime data is complete and the agreement returns to _Active_.

----

![IN161-5_14](assets/IN161-5_14.png)
Send a test message: go to Design -> Integrations and APIs -> IN161-UserXX, open _Artifacts_, click _More_ (...) -> _Deploy_. Then go to Monitor -> B2B Scenarios -> Interchanges, click _Go_, and open your outbound interchange to confirm the ANSI X12 863 message was produced by your own MAG.

----

Continue with: [Exercise 6 - Enhance the mapping with Joule](Exercise-6.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
