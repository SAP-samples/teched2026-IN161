# IN161 – Onboard a trading partner from agreement to live monitoring

## Overview

In this hands-on session, you will onboard a new trading partner using the following SAP Integration Suite capabilities:
- Integration Advisor (IA)
- Trading Partner Management (TPM)
- Cloud Integration (CI)

To get the most out of the session, we recommend familiarity with EDI and related data structures (e.g., IDoc, SOAP, X12, EDIFACT) and a basic understanding of Cloud Integration.

The business process simulated here is part of the procure-to-pay cycle, which typically includes:
- Purchase Order (two-way transaction)
- Shipment Notification
- Invoice

This exercise focuses only on the first transaction.

No additional tools (such as Postman) are required. An iFlow simulates the trading partner by sending an EDIFACT ORDERS message. There is no connected S/4HANA system; instead, another iFlow receives the ORDERS IDoc message and responds with an ORDRSP IDoc sent to TPM via the ProcessDirect adapter. After TPM processes the message, a simulated trading partner receives the ORDRSP as an EDIFACT message over AS2 and forwards it to your personal email inbox for verification.

In Exercise 1, you will reuse existing Message Implementation Guidelines (MIGs), Mapping Guidelines (MAGs), and a complete Agreement. In Exercise 2, you will copy and configure the iFlow that simulates your trading partner and send a test message. In Exercise 3, you will monitor the messages. In Exercise 4, you will onboard the same trading partner again, this time with options to modify the MIGs and MAGs. In Exercise 5, you will create a new Message Implementation Guideline. In Exercise 6, you will create an overlay mapping guideline to adjust the mapping. The final exercise covers functional acknowledgments and how to handle different scenarios.

## Exercises

- [Exercise 1 – Onboard a new trading partner by reference](exercises/Exercise-1.md)
- [Exercise 2 – Create an iFlow for the test message and send it](exercises/Exercise-2.md)
- [Exercise 3 – Monitor the message](exercises/Exercise-3.md)
- [Exercise 4 – Onboard the trading partner by copy](exercises/Exercise-4.md)
- [Exercise 5 – Create a new Message Implementation Guideline](exercises/Exercise-5.md)
- [Exercise 6 – Create a new overlay mapping](exercises/Exercise-6.md)
- [Exercise 7 – Work with the functional acknowledgment](exercises/Exercise-7.md)

Please give us feedback for this session **IN161**

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