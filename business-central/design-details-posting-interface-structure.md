---
    title: Design Details - Posting Interface Structure | Microsoft Docs
    description: This topic provides an overview of the global procedures in the posting interface structure.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: posting, interface, design
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Posting Interface Structure
In the [!INCLUDE[d365fin](includes/d365fin_md.md)] posting interface structure, there are several global procedures that use the same structure:  
  
* RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen. Jnl Line.  
* CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.  
* VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.  
* UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries  
* UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries  
  
## See Also  
[Design Details: Posting Engine Structure](design-details-posting-engine-structure.md)