---
title: "How to: Print Swiss VAT Statements (older version)"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, printing statements"
ms.assetid: 718dd670-da8d-4531-9e72-952e0cc42557
caps.latest.revision: 5
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Print Swiss VAT Statements (older version)
> [!NOTE]  
>  This topic is retained for backward compatibility with the **Swiss VAT Statement** report. For information about using the newer Swiss VAT Statement, see [Swiss VAT Statement](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-r_26100-swiss-vat-statement-$-.md).  
  
 The **Swiss VAT Statement** is the standard calculation report for realizing VAT. You can print this report, and use it for quarterly tax reporting. The **Swiss VAT Statement** includes:  
  
-   A VAT entry.  
  
-   VAT adjusting entries.  
  
-   An accounting sheet.  
  
### To print the Swiss VAT statement  
  
1.  In the **Search** box, enter **Swiss VAT Statement**, and then choose the related link.  
  
    > [!NOTE]  
    >  You will receive a message stating that the **Swiss VAT Statement** will open in the local language.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Closed with Journal no.**|Select the general ledger journals that contain the posting source of the VAT adjusting entries. This field evaluates accounting periods that have already been settled.|  
    |**Open until date**|Select the last date for settling open or unsettled VAT entries.|  
    |**Show Postings**|Specifies if all of the VAT entries for each group will be printed.|  
    |**Show Chargeback**|Specifies if VAT entries and general ledger entries with closed summaries or reposted tax will be printed.|  
    |**Normal rate VAT %**|Select the current typical VAT rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Reduced rate VAT %**|Select the current reduced tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Special rate VAT %**|Select the current special tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Investment\/Operating Purchase VAT G\/L Account**|Select the VAT general ledger account.|  
    |**Own Consumption Bus. Group**|Select the business and product group for own consumptions.|  
    |**Service Foreign Bus. Group**|Select the foreign service business and product group.|  
    |**Export Bus. Group**|Select the business and product group for exports.|  
  
3.  Choose the **Print** button to print the VAT statement or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Swiss Value Added Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-value-added-tax.md)   
 [VAT Rates for Switzerland](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/vat-rates-for-switzerland.md)   
 [VAT Posting Setup](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)   
 [General Ledger Setup](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [VAT Entry](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32)