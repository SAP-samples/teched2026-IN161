# IN161 - Exercise 7 — Working with the Functional Acknowledgment

## Overview

![IN161-7_01](assets/IN161-7_01.png)
In the left-hand navigation, go to *Design* > *B2B Scenarios*.

----
----

![IN161-7_02](assets/IN161-7_02.png)
Open *Agreements* in *B2B Scenarios*.

----
----

![IN161-7_03](assets/IN161-7_03.png)
Open the *Trading Partner Agreement* between your partners (for example, IN161-UserXX and your counterpart).
Use your participant number (XX) where applicable.

----
----

![IN161-7_04](assets/IN161-7_04.png)
Within your *Trading Partner Agreement*, navigate to the *B2B Scenario* section.

----
----

![IN161-7_05](assets/IN161-7_05.png)
Switch the *Trading Partner Agreement* to *Edit* mode to modify the *Functional Acknowledgment* settings.

----
----

![IN161-7_06](assets/IN161-7_06.png)
Select *Interchange (outgoing)* and check the *Receiver Functional Acknowledgment* checkbox.

----
----

![IN161-7_07](assets/IN161-7_07.png)
Go to the *Communication* tab and set *Channel* to the endpoint through which your trading partner will send the CONTRL message.

----
----

![IN161-7_08](assets/IN161-7_08.png)
The channel is already prepared. Select *Company.AS2.Sender*.

----
----

![IN161-7_09](assets/IN161-7_09.png)
Click *Save* to store the changes to the *Trading Partner Agreement*.

----
----

![IN161-7_10](assets/IN161-7_10.png)
Click *Update* so the changes are written to the *Partner Directory*.

Then send a test message (by deploying the *Integration Flow (iFlow)* in the *Package* you copied). After that, open the *B2B Monitor* to view the status of the *Functional Acknowledgment*.

----
----

![IN161-7_11](assets/IN161-7_11.png)
Because the CONTRL message your trading partner sends back is a partial acknowledgment, you can adjust the setting that controls how this partial status is displayed in monitoring. Change the setting and send another message to see the different behavior.

Congratulations — you have finished the TechEd exercise!

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
