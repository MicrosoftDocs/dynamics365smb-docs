---
title: Czech local functionality - Unreliable payer [CZ]
description: This feature uses the treasury department service to obtain published information and indicate the payer status on vendor cards and purchase documents.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: CZ, Czech, Advance payment, Advance invoices, Payables, Finance,  Cash, Cash Desk
ms.date: 09/25/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Unreliable payer in the Czech version

The amendment of VAT Law 235/2004 (§106a) introduced the concept of *Unreliable Payer*. The treasury department is obliged to publish the names of unreliable payers.

This feature uses this service to obtain published information and indicate payer status on vendor cards and purchase documents.

The treasury department also publishes information about registered bank accounts of the payer (only these accounts are allowed for payments). Information about payer registered bank accounts is stored on the vendor bank account cards and used in cash management.

## Key features

- **Unreliable Payer Service Setup** - Setup for managing control parameters (web service, initial check date, limits, service enablement).
- Unreliability Check - On the vendor card, the **Unreliable VAT Payer Check** action is available.
- Automatic Bank Account Creation - In the Unreliable payer entries, the function to create a vendor bank account is available. After importing unreliable payer records, users are prompted to review and optionally open the related page to manage vendor bank accounts.
- Preferred Bank Account Assignment - On the vendor bank account retrieval page, users can mark an account as preferred. This automatically updates the vendor card with the preferred bank account code.
- Quick Access to vendor Bank Accounts - A shortcut is available from the unreliable payer records page to directly open the vendor bank accounts list.
- Purchase Document Check - When issuing a document, the system performs a check for unreliable VAT payer status, verifies the use of a published bank account, and evaluates the configured bank account control limit.
- Bulk Unreliability Import - Allows bulk loading of unreliability entries for multiple vendors.

## Related information

- [Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
