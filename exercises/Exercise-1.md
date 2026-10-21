# IN161 - Exercise 1 - Onboard a new trading partner by reference

Log in to the tenant: [IN161 Tenant](https://url.sap/33psy1)

![Login](assets/exercise1/IN161_Exercise1_1.png)

User: UserXXX, where XXX is your participant number. This number is important and will be used in several places during the exercise. Wherever XXX is mentioned, replace it with your number.
Make sure to use the exact capitalization shown here, as the exercises may not work correctly otherwise.
You will receive the password from your trainers.

----

![Go to B2B Scenarios](assets/exercise1/IN161_Exercise1_2.png)

In the left-hand navigation, go to Design -> B2B Scenarios.

----

![Create Trading Partner](assets/exercise1/IN161_Exercise1_3.png)

Go to Partner Profiles and click Create, then select Trading Partner.

----

![Trading Partner Overview](assets/exercise1/IN161_Exercise1_4.png)

In Overview, enter:
- Company Name: IN161-UserXXX (replace XXX with your number)
- Company Short Name: IN161-UserXXX

Then click Save.

----

![Identifiers - Create](assets/exercise1/IN161_Exercise1_5.png)

Go to Identifiers and click Create in Single Identifiers.

----

![Create X12 identifier](assets/exercise1/IN161_Exercise1_6.png)

Create the identifier that represents your trading partner in the ANSI X12 world. Use the exact casing shown:
- Identification: X.12-TP-E-UserXXX (replace XXX with your number)
- Alias: TP-X.12 4010-Id
- Type System: ASC X12
- Scheme: Duns (Dun & Bradstreet)

Save the identifier.
More information around the identifiers can be found here: [Understanding Identifiers in Agreement](https://help.sap.com/docs/integration-suite/sap-integration-suite/understanding-identifiers-in-agreement?locale=en-US)

----

![Create SAP IDoc identifier](assets/exercise1/IN161_Exercise1_7.png)

Create a second identifier that will be used in the (simulated) S/4HANA QM system. Use the exact casing shown:
- Identification: O123456-UserXXX (this starts with the letter O, not zero)
- Alias: TP-SAP-IDoc-Id
- Type System: SAP S/4HANA On Premise IDoc
- Scheme: N/A

Save the identifier.

----

![Security - Create Signature](assets/exercise1/IN161_Exercise1_8.png)

Go to the Security tab and click Create Signature.

----

![Signature Verification Configuration](assets/exercise1/IN161_Exercise1_9.png)

Create the material for the connection with:
- AS2 Partner ID: O-UserXXX (letter O, not zero; replace XXX with your number)
- Alias: TP-B2B UserXXX (replace XXX with your number)

Save the configuration.

----

![Activate security configuration](assets/exercise1/IN161_Exercise1_10.png)

This configuration must be written to the Partner Directory, so you need to activate it. Click the activation toggle for your configuration.

----

![Confirm activation](assets/exercise1/IN161_Exercise1_11.png)

Confirm the activation by clicking Confirm.

----

![Systems - Create System](assets/exercise1/IN161_Exercise1_12.png)

Next, go to the Systems tab and click Create System.

----

![Create system](assets/exercise1/IN161_Exercise1_13.png)

Enter the system details:
- Name: B2B System
- Alias: TP-B2B System
- Type: B2B System
- Purpose: Dev

Click Save.

The purpose influences the [payload indicator](https://help.sap.com/docs/integration-suite/sap-integration-suite/payload-indicator-in-integration-flow-message-processing?locale=en-US).

----

![Create Type System](assets/exercise1/IN161_Exercise1_14.png)

Assign the type system your trading partner will use. Open the newly created system, go to Type Systems, and click Create Type System.

----

![Assign ASC X12 004010](assets/exercise1/IN161_Exercise1_15.png)

Select Name ASC X12 and Version 004010, then click Add.

----

![Communications - Create Communication](assets/exercise1/IN161_Exercise1_16.png)

Go to the Communications tab and click Create Communication.

----

![Add Communication - Connection](assets/exercise1/IN161_Exercise1_17.png)

In the Add Communication dialog, enter the details so you can later send the X12 863 test-results message to your trading partner:
- Name: AS2.Receiver
- Alias: TP-AS2.Receiver
- Direction: Receiver
- Adapter: AS2

Now, on the Connection tab:
- Recipient URL: https://workshop04a.it-cpi049-rt.cfapps.eu10-003.hana.ondemand.com/as2/as2
- Authentication Type: Basic Authentication
- Credential Name: ESB

----

![Add Communication - Processing](assets/exercise1/IN161_Exercise1_18.png)

Switch to the Processing tab and complete the remaining required fields:
- Own AS2 ID: OwnId-XXX
- Partner AS2 ID: PartnerId-XXX
- Message Subject: Teched IN161 Workshop
- Own E-mail address: your email address (you will receive the ANSI X12 863 test-results message by email)
- Content-Type: application/X.12

Click Save.

----

![Activate communication channel](assets/exercise1/IN161_Exercise1_19.png)

Activate the communication channel so it is deployed to the Partner Directory. Click the activation toggle for AS2.Receiver and confirm with Activate.

----

![Agreements - Create](assets/exercise1/IN161_Exercise1_20.png)

The basic master data for the trading partner has now been saved. Next, you will create a B2B scenario via a Trading Partner Agreement. The required agreement template with all master data details has already been set up for you.
Go to the Agreements tab and click Create.

----

![Select Agreement Template](assets/exercise1/IN161_Exercise1_21.png)

In step 1 of the wizard, select the agreement template named Quality Certificate (Initiator: Ironvale Steel Corp.), then click Next.

----

![Select Agreement Template Version](assets/exercise1/IN161_Exercise1_22.png)

In step 2, select the Draft version of the Quality Certificate template, then click Next.

----

![Select Creation Mode - Bind](assets/exercise1/IN161_Exercise1_23.png)

In step 3, select the Agreement Creation Mode. In this exercise, we use the by-reference variant: choose Bind with Template. This is helpful if all your trading partners expect the same MIG, MAG, etc. Make sure the transaction QualityCertificate_Outbound is selected, then click Next.

----

![Select Trading Partner](assets/exercise1/IN161_Exercise1_24.png)

In step 4, open the Name dropdown and select your trading partner IN161-UserXXX (replace XXX with your number), then click Next.

----

![Review and Open Draft](assets/exercise1/IN161_Exercise1_25.png)

In step 5, review your selections and click Open Draft.

----

![Agreement Overview - Save](assets/exercise1/IN161_Exercise1_26.png)

The agreement draft opens. Keep (or adjust) the agreement name Quality Certificate-UserXXX (replace XXX with your number). Note that your company (Ironvale Steel Corp.) is the initiator and your trading partner is the reactor, and that the outbound message is mapped to ASC X12 004010. Click Save.

----

![Activate the agreement](assets/exercise1/IN161_Exercise1_27.png)

The agreement created in "by-reference" mode shows a one-way, outbound business transaction for sending the Report of Test Results (Mill Test Report) to your trading partner. At this stage it uses an existing mapping that is already available in the tenant, so you can send a message right away – without having built any mapping yourself yet.

In our example this is a mapping that was **migrated from SAP PI/PO** – a very common starting point, because many customers already run working message mappings there and reuse them when they move B2B to Integration Suite. It does not have to come from PI/PO, though: it could just as well be a plain **XSLT** exported from any other system. The point is simply that *some* existing mapping is reused here as-is.

In Exercise 5 you will then create a **Mapping Guideline (MAG)** – the native mapping entity of the SAP Integration Advisor – and use it to **replace** this old (migrated) mapping with one you own and can evolve yourself.

Let's see this in action! Click Activate.

----

![Confirm agreement activation](assets/exercise1/IN161_Exercise1_28.png)

In the Activate Agreement dialog, keep the Activation Mode on Default and click Activate.

----

![Agreement active](assets/exercise1/IN161_Exercise1_29.png)

The Activation Status now shows Active. Your trading partner is onboarded and you can proceed to send the first message.

----

Continue with: [Exercise 2 - Send a test message](Exercise-2.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
