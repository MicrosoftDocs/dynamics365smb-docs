---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Design Details: Posting Interface Structure
In the ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> posting interface structure, there are several global procedures that use the same structure:  
  
-   RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen. Jnl Line.  
  
-   CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.  
  
-   VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.  
  
-   UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries  
  
-   UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries  
  
## See Also  
 [Design Details: Posting Engine Structure](design-details-posting-engine-structure.md)