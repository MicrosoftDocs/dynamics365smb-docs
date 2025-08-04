---
title: Required descriptions in G-L entry
description: When entering general journal lines on a form, the system automatically fills in the description field.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: journal lines, general journal description, Dutch version, Netherlands
ms.date: 03/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Required descriptions in G-L entry

When entering general journal lines on a form, the system automatically fills in the description field. This description is also stored in the G/L entry after posting the journal. For a good audit trail, a more detailed description is desirable, when you post a journal line of type G/L Account.  

To force the user to enter a more detailed description, it's possible to choose if the system must fill in automatically the description of the G/L account or leave the field blank. If the **Omit Default Descr. in Jnl. Field** checkbox on the **G/L Account Card** page is checked, the system doesn't fill in the **Description** field for that G/L account when selected in a general journal line.  

When posting the journal lines, the system checks if all the **Description** fields are filled in. If there's a blank description, an error message appears.  

> [!NOTE]  
> Leaving the description field blank and checking if all the description fields are filled in before posting will only be done on the general journal pages in several application areas and on the local Cash Bank Giro pages.  

## Related information

- [Apply Customer Payments Manually](../../receivables-how-apply-sales-transactions-manually.md)  
- [Create an Audit File for the Tax Authority](how-to-create-an-audit-file-for-the-tax-authority.md)  
- [Understanding the General Ledger and the COA](../../finance-general-ledger.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
