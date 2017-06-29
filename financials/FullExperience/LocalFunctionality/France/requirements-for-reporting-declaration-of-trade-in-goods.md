---
title: "Requirements for Reporting Declaration of Trade in Goods"
ms.custom: na
ms.date: "06-04-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Declaration of Trade in Goods (DEB), about"
ms.assetid: 94a3840f-9240-4313-8f32-ab4ba8973c7c
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# Requirements for Reporting Declaration of Trade in Goods
This topic shows a list of required fields that are needed for reporting Declaration of Trade in Goods \(DEB\) based on the DTI\+ format. For more information, see Export DEB DTI.  
  
 The following fields are required for reporting DEB:  
  
-   **CISD** from the **Company Information** table.  
  
-   **Registration No.** from the **Company Information** table.  
  
-   **VAT Registration No.** from the **Company Information** table.  
  
-   **Name** from the **Company Information** table.  
  
-   **Date** for the statistics period from the **Intrastat Jnl. Line** table.  
  
-   **Transaction Specification** from the **Intrastat Jnl. Line** table.  
  
-   **Quantity** from the **Intrastat Jnl. Line** table must be greater than 0.  
  
-   **Statistical Value** from the **Intrastat Jnl. Line** table must be greater than 0.  
  
> [!NOTE]  
>  The **Export DEB DTI** report exports shipments and receipts in one batch. If you want to report only shipments or receipts, then you must set a filter to remove the lines that are not needed in the **Intrastat Journal** table.  
  
## See Also  
 Export DEB DTI   
 Company Information   
 Intrastat Journal   
 CISD   
 Intrastat Jnl. Line