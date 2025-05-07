---
title: Design Details - Posting Interface Structure
description: This topic provides an overview of the global procedures and design details in the posting interface structure.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: posting, interface, design
ms.date: 06/15/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Posting Interface Structure
In the [!INCLUDE[prod_short](includes/prod_short.md)] posting interface structure, there are several global procedures that use the same structure:  
  
* RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen. Jnl Line.  
* CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.  
* VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.  
* UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries  
* UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries  
  
## Related information  
[Design Details: Posting Engine Structure](design-details-posting-engine-structure.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
