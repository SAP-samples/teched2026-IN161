# IN161 - Exercise 4 - Onboard the Trading Partner by Copying

## Overview
If you create an agreement with the Bind option, you cannot modify the process or change the MIGs and MAGs. Because our trading partner needs slightly different MIGs and MAGs that you will create in the following exercises, we first need an agreement that allows you to modify them. You can do this by instantiating the agreement from the template using the Copy option.

As usual: replace XX with your participant number wherever it appears.

![IN161_038](assets/IN161_038.png)
Go to Design -> B2B Scenarios.

----

![IN161_039](assets/IN161_039.png)
Go to Agreements and open your agreement (IN161-UserXX-bind).

----

![IN161_040](assets/IN161_040.png)
Because you want to create a new agreement for the same trading partner, first deactivate the bound one. Click Deactivate.

----

![IN161_041](assets/IN161_041.png)
Confirm by clicking OK.

----

![IN161_042](assets/IN161_042.png)
Click Create to create a new agreement.

----

![IN161_043](assets/IN161_043.png)
Select the same template as before: IN161-SimpleExerciseTemplate.

----

![IN161_044](assets/IN161_044.png)
Choose Copy from Template, select your trading partner (IN161-UserXX), then click Open Draft.

----

![IN161_045](assets/IN161_045.png)
Name the agreement IN161-UserXX-copy, then click Save and Activate.

----

![IN161_046](assets/IN161_046.png)
Confirm activation by clicking OK.

----

![IN161_047](assets/IN161_047.png)
Before making changes, verify that the new agreement works. Go to Design -> Integrations and APIs.

----

![IN161_048](assets/IN161_048.png)
Open your package IN161-UserXX (replace XX with your number).

----

![IN161_049](assets/IN161_049.png)
Go to Artifacts, click the three dots (...) on the iFlow, then click Deploy. This simulates the trading partner and sends an EDIFACT Order.

----

![IN161_050](assets/IN161_050.png)
Go back to Monitor -> B2B Scenarios.

----

![IN161_051](assets/IN161_051.png)
Click the Interchanges tile.

----

![IN161_052](assets/IN161_052.png)
Click Go and check whether you can find the interchanges for your trading partner. You should see two lines: one for the incoming Order and one for the outgoing Order Response.

----
Continue with: [Exercise 5 - Create a New Message Implementation Guideline](Exercise-5.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
