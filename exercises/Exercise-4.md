# IN161 - Exercise 4 - Onboard the trading partner by copy

## Overview
So far your agreement was created with the **Bind** option. Bind is quick, but it does not let you change the mapping – it always uses the mapping referenced by the template (the one that was migrated from PI/PO). In the next exercises you will build and use your **own Mapping Guideline (MAG)**, and for that you need an agreement created with the **Copy** option.

In this exercise you will therefore **delete** your bind agreement and recreate it from the same template using **Copy from Template**. For now it will still use the migrated PI/PO mapping, so you can confirm it works before you change anything.

As usual, replace XXX with your participant number wherever it appears.

> Note: Screenshots for this exercise still need to be captured and uploaded (file names `assets/IN161_Exercise4_N.png`).

----

![Open Agreements](assets/IN161_Exercise4_1.png)

In the left-hand navigation, go to Design -> B2B Scenarios and open the Agreements tab.

----

![Open your bind agreement](assets/IN161_Exercise4_2.png)

Open your agreement Quality Certificate-UserXXX (the one you created with Bind in Exercise 1).

----

![Deactivate the agreement](assets/IN161_Exercise4_3.png)

Because you want to replace it, first deactivate it. Click Deactivate and confirm.

----

![Delete the agreement](assets/IN161_Exercise4_4.png)

Now delete the agreement: click the More menu (...) -> Delete (or the Delete button) and confirm.

----

![Create a new agreement](assets/IN161_Exercise4_5.png)

Click Create to create a new agreement.

----

![Select Agreement Template](assets/IN161_Exercise4_6.png)

In step 1 of the wizard, select the agreement template named Quality Certificate (Initiator: Ironvale Steel Corp.), then click Next.

----

![Select Template Version](assets/IN161_Exercise4_7.png)

In step 2, select the Draft version, then click Next.

----

![Select Creation Mode - Copy](assets/IN161_Exercise4_8.png)

In step 3, select the Agreement Creation Mode. This time choose **Copy from Template** (not Bind). Copy creates an independent agreement in which you can change the MIGs and MAGs. Make sure the transaction QualityCertificate_Outbound is selected, then click Next.

----

![Select Trading Partner](assets/IN161_Exercise4_9.png)

In step 4, open the Name dropdown and select your trading partner IN161-UserXXX, then click Next.

----

![Review and Open Draft](assets/IN161_Exercise4_10.png)

In step 5, review your selections and click Open Draft.

----

![Name and Save the agreement](assets/IN161_Exercise4_11.png)

Keep (or adjust) the agreement name Quality Certificate-UserXXX, then click Save.

----

![Activate the agreement](assets/IN161_Exercise4_12.png)

Click Activate, keep the Activation Mode on Default in the dialog, and click Activate. Wait until the Activation Status shows Active.

----

![Send a test message and monitor](assets/IN161_Exercise4_13.png)

Verify that the copied agreement works. Go to Design -> Integrations and APIs -> IN161-UserXXX, open Artifacts, click More (...) -> Deploy to send a test message. Then go to Monitor -> B2B Scenarios -> Interchanges, click Go, and confirm you can see your outbound ANSI X12 863 interchange.

----

Continue with: [Exercise 5 - Create your own Mapping Guideline (MAG) using proposals](Exercise-5.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
