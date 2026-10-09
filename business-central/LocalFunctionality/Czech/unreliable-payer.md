---
title: Czech local functionality - Unreliable payer [CZ]
description: Learn how the Czech Unreliable Payer feature uses the Czech tax authority's web service to obtain published information and indicate the payer status on vendor cards and purchase documents.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: CZ, Czech, unreliable payer, unreliable VAT payer, unreliable payer check, tax authority, unreliable payer service
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Unreliable payer in the Czech version

The amendment of VAT Law 235/2004 (§106a) introduced the concept of *Unreliable Payer*. The tax authority is obliged to publish the names of unreliable payers.

This feature uses a web service from the Czech tax authority (Financial Administration) to retrieve published information and indicate payer status on vendor cards and purchase documents.

The tax authority also publishes information about the payer's registered bank accounts (only these accounts are allowed for payments). Information about payer registered bank accounts is stored on the vendor bank account cards and used in cash management.

## Key features

- **Unreliable Payer Service Setup**: Setup for managing control parameters (web service, initial check date, limits, service enablement).
- **Unreliability Check**: On the vendor card, the **Unreliable VAT Payment Check** action is available.
- **Automatic Bank Account Creation**: The unreliable payer entries include a function to create a vendor bank account. After you import unreliable payer entries, you're prompted to review and, if needed, open the related page to manage vendor bank accounts.
- **Preferred Bank Account Assignment**: On the **Get Vendor Bank Account Code** page, you can mark an account as preferred. This automatically updates the vendor card with the preferred bank account code.
- **Quick Access to Vendor Bank Accounts**: A shortcut is available from the **Unreliable Payer Entries** page to directly open the vendor bank accounts list.
- **Purchase Document Check**: When you release a purchase document, Business Central checks for unreliable VAT payer status, verifies the use of a published bank account, and evaluates the configured bank account control limit.
- **Bulk Unreliability Import**: Lets you bulk load unreliability entries for multiple vendors.

## Related information

- [Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
