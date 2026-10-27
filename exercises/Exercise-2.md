# IN161 - Exercise 2 - Send a test message

## Overview
In this exercise, you will copy an existing iFlow into your own package and configure it to simulate the sending S/4HANA QM system. When deployed, the iFlow pushes a ZQMOUTTC IDoc (the quality certificate) into TPM, which maps it to an ANSI X12 863 message and sends it to your trading partner.
Replace XXX with your participant number wherever it appears.

![Navigate to Integrations and APIs](assets/exercise2/IN161_2_01.png)

In the left-hand navigation, go to Design -> Integrations and APIs.

----

![Create a new package](assets/exercise2/IN161_2_02.png)

Click Create to create your own integration package.

----

![Name the package](assets/exercise2/IN161_2_03.png)

Enter the package name IN161-UserXXX (replace XXX with your number), then click Save.

----

![Package saved - go back](assets/exercise2/IN161_2_04.png)

Your package has been saved. Click the breadcrumb link Integrations and APIs to return to the package list.

----

![Navigate to SimulatorFlow](assets/exercise2/IN161_2_05.png)

In the package list, click IN161-SimulatorFlow to open it.

----

![Open Artifacts tab](assets/exercise2/IN161_2_06.png)

Click the Artifacts tab to see the iFlow contained in the package.

----

![Copy the iFlow](assets/exercise2/IN161_2_07.png)

Click the three dots (...) next to the iFlow send-Qualitydata, then click Copy.

----

![Rename and select target package](assets/exercise2/IN161_2_08.png)

In the Copy dialog:
- Append _XXX to the name so it reads send-Qualitydata_XXX (replace XXX with your number).
- Click Select to choose the target package.

----

![Select your package](assets/exercise2/IN161_2_09.png)

In the Package Selection dialog, select IN161-UserXXX (replace XXX with your number).

----

![Confirm the copy](assets/exercise2/IN161_2_10.png)

The target package is now set to IN161-UserXXX. Click Copy to copy the iFlow to your package.

----

![Navigate to your package](assets/exercise2/IN161_2_11.png)

The copy was successful. Click Navigate to open your package IN161-UserXXX.

----

![Configure the iFlow](assets/exercise2/IN161_2_12.png)

In your package, go to the Artifacts tab. Click the three dots (...) next to send-Qualitydata_XXX and click Configure.

----

![Set your user number and deploy](assets/exercise2/IN161_2_13.png)

In the Configure dialog, set Usernumber to XXX (replace XXX with your number), then click Deploy.

----

![Confirm deployment](assets/exercise2/IN161_2_14.png)

Confirm the deployment by clicking Deploy. If the dialog shows a Confirm transaction handling configuration checkbox, check it first, then click Deploy.

After deployment, the simulated QM system sends a ZQMOUTTC IDoc. TPM maps it to an ANSI X12 863 message and sends it to your trading partner.

----

![Inside the iFlow](assets/exercise2/IN161_2_15.png)

Optionally, open your iFlow send-Qualitydata_XXX to see how it works. The integration process starts with a timer start event that fires once when the iFlow is deployed – that is what triggers the ZQMOUTTC IDoc to be sent, without any manual request. The flow then builds the IDoc payload and hands it over to TPM for mapping and delivery to your trading partner.

----
Continue with: [Exercise 3 - monitor the message](Exercise-3.md)

Please give us feedback for this session **IN161**. Scan the QR code to open the mobile app, then navigate to this session (IN161) to give your feedback.

![QR Code](assets/survey_QR.png)
