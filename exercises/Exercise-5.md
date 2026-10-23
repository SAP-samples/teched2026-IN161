# IN161 - Exercise 5 — (Optional) Create Target Message Implementation Guideline(MIG)

## Overview

Prerequisite: Download the sample payload [X12-863.txt](Payload/X12-863.txt) from the Payload folder.  

In this exercise you will create the Trading Partner specific Target MIG.The Creation and designing of a MIG includes the: 

  - creation of the required target Message structure easily from an existing EDI payload and refine of the nodes,
    especially qualification of the nodes, 
  - precision of the properties of leaf nodes such as length, cardinality, format,
    and primitive type.    
  - creation and assignment of codelists, as well as the customizing of elements at the leaf node level 

The creation of human-readable descriptions, the setting of integrity conditions via assertions, adds to a semantically enriched 
MIG design. The more precise you are in finalizing your MIG, the easier all the steps afterward will be at the mapping steps as wel on the life-cycle management of the artifcats involved.

You would not need to preapre all these mentioend above, however we would like to give you the most important steps you need to consider to build your Message Implementation Guidelines for your future projects! 

<u>Let's start with the X12 message creation from a payload:</u> 

Goto Message Implmenentation Guidelines Overview screen, Select in the Create button dropdown the "Create by Payload" option.
![IN161_5_01](assets/exercise5/IN161_5_01.png) 

Drop in or select the prepared Payload and navigate through the guided steps by confirming the proposed selection for the X12 Type System, 863 Message, with the selected Version of 004010 . 
![IN161_5_02](assets/exercise5/IN161_5_02.png)
![IN161_5_03](assets/exercise5/IN161_5_03.png) 
![IN161_5_04](assets/exercise5/IN161_5_04.png)

Select Envelope, and navigate to the "Sample Payload" selection Step.
![IN161_5_05](assets/exercise5/IN161_5_05.png) 

Select all offered options inlcuding "Set Example Values" as indicated by the Screenshot
![IN161_5_06](assets/exercise5/IN161_5_06.png) 

Go to the Qualification step and select the nodes as indicated by the Screenshot
![IN161_5_07](assets/exercise5/IN161_5_07.png) 

Hit the Create button on the lower right corner. The MIG Creation Dialog opens where you need to specify the Name and Direction of the MIG as well the Business Context Information. 
Specify: 
 	MIG Name: "UserXXX - 863 - Target MIG (replace XXX with your number) 
 	Direction : Out 
Own Business Context: Select Country Germany ( 1 would be enough...) 
![IN161_5_08](assets/exercise5/IN161_5_08.png) 

<u>Let´s start refining the created MIG with the help of the in-built accelerator features like the proposal service, qualification and many more!</u>

As we have our message implementation guideline with the message **863**, you need to select the fields that are relevant to your scenario and build the MIG accordingly. You can also get proposals from the application on which fields might be most relevant for you based on existing MIGs.
Here are a few considerations to be mindful of before you work with MIG:
In the MIG structure, if there is one or more nodes with the checkbox selected, that node is a mandatory element as defined by the original message template.
If you want to edit details associated with the nodes like Name, Simple Type Properties, Description, etc., you must select the checkbox associated with the node.
You can maintain the qualifier markers if it was defined by the source template. You can also maintain additional markers by selecting an element that can be qualified, editing the property sheet, and maintain the instance by selecting the qualifier values. 


Navigate the the Second Tab called "Structure" and select the "Get Proposal" button from the right upper corner. 
 ![IN161_5_09](assets/exercise5/IN161_5_09.png) 

In the Structure you will see a new Column called "Confidence" with blue bars and beside selected Nodes like **ST** under **863** selection button 
Navigate to the node **ST** select the two boxes action and select the proposed Qualification Value _863_ to qualify the **ST** Segement from the Element **143** _Transaction Set Identifier Code_. This qualification is constant value which will be automatically taken over at the Mapping Excercise.
  ![IN161_5_10](assets/exercise5/IN161_5_10.png)
   ![IN161_5_11](assets/exercise5/IN161_5_11.png)  

In SAP Integration Advisor MIGs (Message Implementation Guidelines), the qualification of EDI structure nodes is one of the most powerful modeling techniques because it adds business meaning (semantics) directly into the message structure instead of leaving that interpretation for the mapping runtime.The message structure is composed of logically related pieces of information grouped into generic data segments. You can customize and precisely specify the context of generic elements in your MIG message structure to provide business meaning to the rest of the data in a segment.

To do so navigate to the Element **BTR** select the two boxes action and select the proposed Qualification Value _00_
 ![IN161_5_11](assets/exercise5/IN161_5_12.png) 

You would need to execute the similar activity for the following elements mentioned below. 

Navigate to the Element **PID** select the two boxes action and select the proposed Qualification Value _F_
 ![IN161_5_12](assets/exercise5/IN161_5_13.png) 

To give a bit more insights why a qualification is relevant.For example, a generic element like N1-repeatable group of segments consists of Name, or Address or Reference information is unclear at the semantic level as to which identity Type of name or address the message interface refers to. As a result, additional information is required to remove any ambiguity related to the semantic purpose of a segment. Qualifiers can be used to specify which type of repeatable segment types including name, address is stored within a particular instance of a data segment.

An address segment generally consists of a similar set of fields such as - street, city, state, postal code, and country. However, there may be more than one set of addresses such as a delivery address, a contact address, or a billing address. In these situations, you could use a common address segment structure and then use a qualifier to specify which type of address is stored within a particular instance of a data segment.

Qualifiers are provided by a leaf node (qualifying node) in the form of codelists and related code values. In our example **BY** = **Buyer** or **ST** = **Ship To**. 
 A leaf node can qualify a group node or another leaf node (peer node) only if it has a codelist assigned to it. The link between the qualifying node (leaf node) and the node you want to qualify (qualifiable node) is expressed by a qualifier marker arrow in gray. A qualifier marker can go from a qualifying element to a parent group element or a peer element at the same level. It helps identify the elements that can be qualified. Qualifier markers are either automatically provided by message templates from type systems, or you can create your own qualifier markers to suit your business context.   
A qualified group or peer leaf node is indicated by a blue arrow marker from the qualifying leaf node to the qualified node along with the qualifier value provided by the selected code values. The name of the qualifier value is appended to the qualified instance.

<u> Let´s precise the semantical menaing of the **N** element by qualifiying it's multiple occurences</u> 

Navigate to the Element **N1** select the two boxes action and select the proposed Qualification Value _ST_
 ![IN161_5_12](assets/exercise5/IN161_5_14.png)

A qualified Element of **N1** was created with the qualified value _ST_. We need to have multiple **N1** Segments as such we need to qualify 2 additional elements with the qualified value _SE_ For the Selling Party and _BY_ for the Buyer Party. This qualification enables a direct mapping of the source elements from the IDoc structure to the Target structure without any additional functional mapping steps. 
To qualify another Enumreation Value for the **N1** Segment we will duplicate the Node by selecting the qualified **N1** right Mouse click and select from the action _"Duplicate Qualified Node"_ with the value _"SE"_ as indicated on the screenshot. 
![IN161_5_12](assets/exercise5/IN161_5_15.png)
![IN161_5_12](assets/exercise5/IN161_5_16.png)

We do the same for the newly created qualified **N1** node as before as such duplicate the Node by selecting the qualified **N1** right Mouse click and select from the action _"Duplicate Qualified Node"_ and select the _"BY"_
![IN161_5_12](assets/exercise5/IN161_5_17.png)

Next navigate to the Element **DTM** right mouse click and select _"Qualify Node..."_ 
![IN161_5_12](assets/exercise5/IN161_5_18.png)

Select the Value _"050"_ from the Enumeration lsit and click **"Create"** to qualify the **DTM** segment. 

Once you verified the actions you can filter out the selected Elements. Navigate to the Filter of the First Column **Node** and set a filter to _"Show Selected Nodes"_
![IN161_5_12](assets/exercise5/IN161_5_19.png)

Save your changes! 

**As a Summary of this excercise:**
The most important key fact is the Node qualification in Integration Advisor! 
<u>It is powerful because it:</u>

- Removes ambiguity from repeated segments.
- Improves semantic matching during MAG generation.
- Eliminates many conditional mapping rules and filters. 

Every qualifier identified and modeled in the MIG is one less conditional mapping function you need to build and maintain later!!

Continue with: [Exercise 6 - Create your own Mapping Guideline (MAG) using proposals](Exercise-6.md)

Please give us feedback for this session **IN161**

![QR Code](assets/survey_QR.png)
