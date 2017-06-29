---
title: "Design Details: Posting Interface Structure"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general journal post line, posting interface structure"
  - "posting interface structure"
ms.assetid: e54a1149-b00a-41d0-8e93-8fea84044863
caps.latest.revision: 2
ms.author: "edupont"
manager: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Details: Posting Interface Structure
In the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] posting interface structure, there are several global procedures that use the same structure:  
  
-   RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen. Jnl Line.  
  
-   CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry\-Apply Posted Entries.  
  
-   VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry\-Apply Posted Entries.  
  
-   UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry\-Apply Posted Entries  
  
-   UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry\-Apply Posted Entries  
  
## See Also  
 [Design Details: Posting Engine Structure](../ApplicationDesign/design-details-posting-engine-structure.md)