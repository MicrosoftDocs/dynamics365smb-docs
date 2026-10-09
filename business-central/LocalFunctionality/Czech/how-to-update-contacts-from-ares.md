---
title: Czech local functionality - Update contacts from ARES
description: Learn how to update contact information in Business Central using ARES, the Czech system for retrieving data on registered economic entities.
author: v-makune
ms.service: dynamics-365-business-central
ms.topic: concept-article
ms.search.keywords: CZ, Czech, Advance payment, Advance invoices, Payables, Finance,  Cash, EET, Cash Desk
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Updating contacts from ARES in the Czech version

ARES stands for Access to Register of Economic Subjects. ARES is an information system that lets you retrieve information on economic entities registered in the Czech Republic.

To turn on the integration, go to the **Registration No. Validation Service Setup** page, and fill in the **Service Endpoint** field. After you turn on the **Enabled** toggle, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] automatically checks the registration number against ARES whenever you enter or change the **Registration Number** field on the Contact, Vendor, or Customer card. If the information that's returned from ARES doesn't fully match the record, the **Registration No. Check** page opens so you can review and choose which fields to update (Name, Address, City, Post Code).

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
