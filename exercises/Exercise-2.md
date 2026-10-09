# IN161 - Exercise 2 - Send a test message

## Overview
In this exercise, you will copy an existing iFlow into your own package and configure it to simulate the sending S/4HANA QM system. When deployed, the iFlow pushes a ZQMOUTTC IDoc (the quality certificate) into TPM, which maps it to an ANSI X12 863 message and sends it to your trading partner.
Replace XXX with your participant number wherever it appears.

![IN161_024](assets/IN161_024.png)

Go to Design -> Integrations and APIs.

----

![IN161_025](assets/IN161_025.png)

Create your own package by clicking Create.

----

![IN161_026](assets/IN161_026.png)

Name the package IN161-UserXXX (replace XXX with your number).

----

![IN161_027](assets/IN161_027.png)

Navigate to the package IN161-SimulatorFlow.

----

![IN161_028](assets/IN161_028.png)

Open the Artifacts tab, click the three dots (...), then click Copy.

----

![IN161_029](assets/IN161_029.png)

In the Copy dialog:
- Rename the iFlow to IN161 - Send X12 863_UserXXX (replace XXX with your number).
- Select your package IN161-UserXXX (replace XXX with your number).
- Click Copy.

----

![IN161_030](assets/IN161_030.png)

To configure the copied iFlow, click Navigate to open the new iFlow.

----

![IN161_031](assets/IN161_031.png)

Open Artifacts, click the three dots (...), then click Configure.

----

![IN161_032](assets/IN161_032.png)

In the Configure screen:
- Set UserId to UserXXX (replace XXX with your number).
- Click Save, then Deploy.

----

![IN161_033](assets/IN161_033.png)

Confirm the deployment by clicking Yes.
After deployment, the simulated QM system sends a ZQMOUTTC IDoc. TPM maps it to an ANSI X12 863 message and sends it to your trading partner.

----
Continue with: [Exercise 3 - monitor the message](Exercise-3.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
