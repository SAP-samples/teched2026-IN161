# IN161 – Onboard a trading partner from agreement to live monitoring

## Overview

In this hands-on session, you will onboard a new trading partner and exchange a real business message using the following SAP Integration Suite capabilities:
- Integration Advisor (IA)
- Trading Partner Management (TPM)
- Cloud Integration (CI)

To get the most out of the session, we recommend familiarity with EDI and related data structures (e.g., IDoc, X12, EDIFACT) and a basic understanding of Cloud Integration. Experience with SAP Process Integration/Orchestration (PI/PO) message mappings is helpful but not required.

## The business process

The scenario comes from the **steel industry**. Whenever a steel producer ships material, it must provide the customer with **quality/inspection certificates** – comparable to a mill test certificate (e.g., EN 10204 3.1) – that document the chemical composition and mechanical properties of the delivered material (such as tensile strength, yield strength, elongation, or hardness). More and more customers require these certificates **electronically via EDI** instead of as paper or PDF, so that the measured values can flow straight into their goods-receipt inspection and release decisions.

In SAP S/4HANA Quality Management (QM), these inspection results are issued as an IDoc. In our scenario a company-specific message type **ZQMOUTTC** is used – it is based on the standard quality-data IDoc **QALITY02** and extended for steel-industry requirements. The trading partner expects the data as an **ANSI X12 863 – Report of Test Results** (version **004010**).

This is a **one-way, outbound** process with a **single transaction**:

```
S/4HANA QM  ──ZQMOUTTC IDoc──▶  (ProcessDirect)  ──▶  TPM / Integration Advisor
                                                         │  map ZQMOUTTC → X12 863
                                                         ▼
                                           Trading Partner  ◀──AS2 (X12 863)──
```

There is no connected S/4HANA system; instead, an iFlow simulates the sending QM system by pushing a ZQMOUTTC IDoc into TPM via the ProcessDirect adapter. TPM maps it to an ANSI X12 863 message and sends it to your trading partner over AS2. For verification, the message is also forwarded to your personal email inbox. No additional tools (such as Postman) are required.

## What this session is really about: reusing your mapping investment

Many customers already run working **message mappings (mmaps)** in SAP PI/PO. When moving B2B/EDI to Integration Suite, that investment does not have to be thrown away: a PI/PO message mapping can be **migrated into an Integration Advisor Mapping Guideline (MAG)**.

The exercises take you through the full journey:
1. First you use a mapping that has **already been migrated from PI/PO** and is available in the tenant – so you can send a message quickly.
2. Then you build **your own MAG** from scratch and let the Integration Advisor knowledge base **propose** the mapping for you.
3. Finally you enhance that MAG with custom **mapping functions** (XSLT/XPath) – for the steel-industry-specific transformations that a standard proposal cannot cover.

Understanding this path matters because PI/PO is approaching end of maintenance: being able to carry existing mappings forward, and then extend them with proposals and AI, is what makes the move to Integration Suite fast and low-risk.

Two optional exercises round out the picture: creating the target Message Implementation Guideline (MIG) yourself, and – on the operations side – reprocessing a message in the B2B Monitor by duplicating and retrying an interchange.

## Exercises

- [Exercise 1 – Onboard a new trading partner by reference](exercises/Exercise-1.md)
- [Exercise 2 – Send a test message](exercises/Exercise-2.md)
- [Exercise 3 – Monitor the message](exercises/Exercise-3.md)
- [Exercise 4 – Onboard the trading partner by copy](exercises/Exercise-4.md)
- [Exercise 5 – (Optional) Create the target Message Implementation Guideline (MIG)](exercises/Exercise-5.md)
- [Exercise 6 – Create your own Mapping Guideline (MAG) using proposals](exercises/Exercise-6.md)
- [Exercise 7 – Enhance the Mapping Guideline (MAG) with custom functions](exercises/Exercise-7.md)
- [Exercise 8 – (Bonus) Duplicate and retry an interchange](exercises/Exercise-8.md)

Please give us feedback for this session **IN161**. Scan the QR code to open the mobile app, then navigate to this session (IN161) to give your feedback.

![QR Code](exercises/assets/survey_QR.png)

## Contributing

Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support
Support for the content in this repository is available during the scheduled online session for which this content was designed.

## License
Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved.

This project is licensed under the Apache License, version 2.0, except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
