---
title: Set up VERIFACTU [ES]
description: Learn how to set up and use VERIF*ACTU in the Spanish version of Business Central.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Verifactu, SFI, e-invoice, Spanish version
ms.search.form: 
ms.date: 07/11/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# VERI*FACTU rules in Spain

VERI*FACTU is a regulatory framework introduced by the Spanish government to modernize and secure electronic invoicing systems, with the primary goal of combating tax fraud and enhancing transparency in business transactions. It is governed by Royal Decree 1007/2023, later amended by Royal Decree 254/2025, and forms part of Spain’s broader Anti-Fraud Law 11/2021.

VERI*FACTU refers to a “verifiable invoicing system”—a type of computerized invoicing system (SIF) that can optionally send invoice records in real time to the Spanish Tax Agency (AEAT).

Businesses in Spain have an option to use the [SII](sii-setup.md) and in this case VERI*FACTU (SIF) rules will not apply to them. [SII](sii-setup.md) can be enforced for large companies with an annual turnover exceeding the tharshhold, but businesses may also opt in voluntarily to report SII. For all other cases, SIF will be mandatory.

## Set up VERI*FACTU in the Spanish version

Dynamics 365 Business Central supports VERI*FACTU frameworks using integration with the B2Brouter API through our default connector. To setup this mode, follow these steps:

### Disbale SII module 



### Enable B2BRouter connector



> [!IMPORTNAT]
> Microsoft will continue to invest into E-Document framework in Business Central to enable full compliance with VERI*FACTU without any additional integration. All news will be updated here.


## Related information

- [SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
