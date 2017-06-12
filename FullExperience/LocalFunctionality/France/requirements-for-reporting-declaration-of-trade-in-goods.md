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
This topic shows a list of required fields that are needed for reporting Declaration of Trade in Goods \(DEB\) based on the DTI\+ format. For more information, see [\($ B\_10821 Export DEB DTI $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-b_10821-export-deb-dti-$-.md).  
  
 The following fields are required for reporting DEB:  
  
-   **\($ T\_79\_10811 CISD $\)** from the **\($ T\_79 Company Information $\)** table.  
  
-   **\($ T\_79\_20 Registration No. $\)** from the **\($ T\_79 Company Information $\)** table.  
  
-   **\($ T\_79\_19 VAT Registration No. $\)** from the **\($ T\_79 Company Information $\)** table.  
  
-   **\($ T\_79\_2 Name $\)** from the **\($ T\_79 Company Information $\)** table.  
  
-   **\($ T\_263\_5 Date $\)** for the statistics period from the **\($ T\_263 Intrastat Jnl. Line $\)** table.  
  
-   **\($ T\_263\_28 Transaction Specification $\)** from the **\($ T\_263 Intrastat Jnl. Line $\)** table.  
  
-   **\($ T\_263\_15 Quantity $\)** from the **\($ T\_263 Intrastat Jnl. Line $\)** table must be greater than 0.  
  
-   **\($ T\_263\_18 Statistical Value $\)** from the **\($ T\_263 Intrastat Jnl. Line $\)** table must be greater than 0.  
  
> [!NOTE]  
>  The **\($ B\_10821 Export DEB DTI $\)** report exports shipments and receipts in one batch. If you want to report only shipments or receipts, then you must set a filter to remove the lines that are not needed in the **\($ N\_311 Intrastat Journal $\)** table.  
  
## See Also  
 [\($ B\_10821 Export DEB DTI $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-b_10821-export-deb-dti-$-.md)   
 [\($ T\_79 Company Information $\)](assetId:///2a44e662-0d42-429e-8131-e0012a89996a)   
 [\($ N\_311 Intrastat Journal $\)](assetId:///ab8fb127-829f-496a-96af-24bdc3457595)   
 [\($ T\_79\_10811 CISD $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_79_10811-cisd-$-.md)   
 [\($ T\_263 Intrastat Jnl. Line $\)](assetId:///eba14eeb-fb3c-447b-af4d-9e18d83e93d8)