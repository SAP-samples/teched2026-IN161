# IN161 - Exercise 1 - Onboard a new trading partner by reference

Log in to the tenant: [IN161 Tenant](https://url.sap/nvxsuf)
![IN161_001](assets/IN161_001.png)
User: UserXX, where XX is your participant number. This number is important and will be used in several places during the exercise. Wherever XX is mentioned, replace it with your number.
Make sure to use the exact capitalization shown here, as the exercises may not work correctly otherwise.
You will receive the password from your trainers.
This is the tenant you will work on: [IN161 Tenant](https://url.sap/nvxsuf)

----
----

![IN161_002](assets/IN161_002.png)

In the left-hand navigation, go to Design -> B2B Scenarios.

----
----

![IN161_003](assets/IN161_003.png)

Go to Partner Profiles and click Create, then select Trading Partner.

----
----

![IN161_004](assets/IN161_004.png)

In Overview, enter:
- Company Name: IN161-UserXX (replace XX with your number)
- Company Short Name: IN161-UserXX

----
----

![IN161_005](assets/IN161_005.png)

Go to Identifiers and click Create in Single Identifiers.

----
----

![IN161_006](assets/IN161_006.png)

In the pop-up, create the identifier that will later be used in the (simulated) S/4 system. Use the exact casing shown:
- Identification: O-UserXX (this is the letter O, not zero)
- Alias: TP-SAP-IDoc-ID
- Type System: SAP S/4HANA On Premise IDoc
- Scheme: N/A
Save the identifier.

----
----

![IN161_007](assets/IN161_007.png)

Create another identifier that will later be used in the (simulated) trading partner system. Use the exact casing shown:
- Identification: UNEDI_TP_E_UserXX (replace XX with your number)
- Alias: TP-UN-EDIFACT D.02A-ID
- Type System: UN/EDIFACT
- Scheme: DUNS (Data Universal Numbering System) — use the one with qualifier 1 (there are two DUNS entries)

Save the identifier.
More information around the identifiers can be found here: [Understanding Identifiers in Agreement](https://help.sap.com/docs/integration-suite/sap-integration-suite/understanding-identifiers-in-agreement?locale=en-US)

----
----

![IN161_008](assets/IN161_008.png)

Go to the Security tab and click Create.

----
----

![IN161_009](assets/IN161_009.png)

Create the material for the incoming connection with:
- AS2 Partner ID: O-UserXX (letter O, not zero; replace XX with your number)
- Alias: TP-B2B UserXX (replace XX with your number)

Save the configuration.

----
----

![IN161_010](assets/IN161_010.png)

This configuration must be written to the Partner Directory, so you need to activate it. Click the check mark and confirm the activation.

----
----

![IN161_011](assets/IN161_011.png)

Next, go to Systems and click Create System.

----
----

![IN161_012](assets/IN161_012.png)

Enter the system details:
- Name: B2B System
- Alias: TP-B2B System
- Type: B2B System
- Purpose: Dev

Click Save.

The purpose influences the [payload indicator](https://help.sap.com/docs/integration-suite/sap-integration-suite/payload-indicator-in-integration-flow-message-processing?locale=en-US) 

Now click on the created system to open it and continue with the exercise.
----
----

![IN161_013](assets/IN161_013.png)

Assign the type system your trading partner will use. Open the newly created system, go to Type Systems, and click Create Type System.

----
----

![IN161_014](assets/IN161_014.png)

Select UN/EDIFACT and Version D.02A S3, then click Add.

----
----

![IN161_015](assets/IN161_015.png)

Go to Communications and click Create Communication.

----
----

![IN161_016](assets/IN161_016.png)

In the Add Communication dialog, enter the details so you can later send the Order Response message to your trading partner:
- Name: AS2.Receiver
- Alias: TP-AS2.Receiver
- Direction: Receiver
- Adapter: AS2

Now, on the Connection tab:
- Recipient URL: https://workshop-eu-03a.it-cpi033-rt.cfapps.eu10-005.hana.ondemand.com/as2/as2
- Authentication Type: Basic Authentication
- Credential Name: ESB

----
----

![IN161_017](assets/IN161_017.png)

Switch to the Processing tab and complete the remaining required fields:
- Own AS2 ID: OwnId-XX
- Partner AS2 ID: PartnerId-XX
- Message Subject: IN161 – Onboard a trading partner from agreement to live monitoring
- Own email address: your email address (you will receive the EDIFACT Order Response message by email)
- Content Type: application/EDIFACT   

Click Save.

----
----

![IN161_018](assets/IN161_018.png)

Create the second communication channel so you can receive the EDIFACT Order message from your trading partner:
- Name: AS2.Sender
- Alias: TP-AS2.Sender
- Direction: Sender
- Adapter: AS2
- Security Configuration Mode: Profile
- AS2 Partner ID: O-UserXX (should be prefilled with your number)  
Click Save.

----
----

![IN161_019](assets/IN161_019.png)

The basic master data for the trading partner has now been saved. Next, you will create a B2B scenario via a Trading Partner Agreement. The required agreement template with all master data details has already been set up for you.
Go to Agreements and click **Create**.

----
----

![IN161_020](assets/IN161_020.png)

Select the agreement template named IN161-SimpleExerciseTemplate and click Next.

----
----

![IN161_021](assets/IN161_021.png)

In this exercise, we will use the by-reference variant. This is helpful if all your trading partners expect the same MIG, MAG, etc.
Click Bind with Template, select your trading partner IN161-UserXX in the dropdown, and click Open Draft.

----
----

![IN161_022](assets/IN161_022.png)

Change the agreement name to IN161-UserXX-bind (replace XX with your number), then click Save.

----
----

![IN161_023](assets/IN161_023.png)
The agreement created from the template in "by-reference" mode shows a two-way business transaction guided by the UN/CEFACT Modelling Methodology. This B2B scenario defines a structured sequence of business transactions between a company and its trading partner to fulfill contractual obligations, ensuring efficient and compliant business collaboration.
Let's see this in action!
**Click 'Activate'**. After activation, your trading partner is onboarded and you can proceed to send the first message.

----
----

Continue with: [Exercise 2 - create an iFlow for the test message and send the message](Exercise-2.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
