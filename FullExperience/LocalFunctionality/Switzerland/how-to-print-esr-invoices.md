---
title: "How to: Print ESR Invoices"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "ESR payments, coupons"
  - "ESR payments, printing invoices"
ms.assetid: 1dbbe25b-6ebd-4768-bc0c-46265ef430bb
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Print ESR Invoices
You can print an Einzahlungsschein mit Referenznummer \(ESR\) payment slip in the following ways:  
  
-   As part of the sales invoice ESR.  
  
-   As a separate document called an ESR coupon.  
  
 The sales invoice ESR report corresponds with the sales invoice that is accompanied by an additional ESR coupon. By using the sales ESR coupon report, you can print the blue deposit slip.  
  
> [!NOTE]  
>  You must select a printer and select settings during the ESR payment module installation to print the deposit slip correctly. For more information, see the [\($ T\_78 Printer Selection $\)](assetId:///e7c3bf24-9d03-418b-9826-d6125b34a516) table.  
  
 The following procedure describes how to print ESR sales invoices, but the same steps also apply for printing ESR coupons.  
  
### To print ESR invoices  
  
1.  In the **Search** box, enter **Invoice ESR**, and then choose the related link.  
  
2.  In the **\($ B\_3010532 Sales Invoice ESR $\)** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_3010532\_F\_1\_1150006 No. of copies $\)**|Enter the required number of report copies.|  
    |**\($ B\_3010532\_F\_1\_1150003 ESR Bank $\)**|Select the ESR bank code that is to be printed in the report.<br /><br /> If the value in this field is \<Blank\> and the ESR payment method code is not defined in the **\($ T\_3010531 ESR Setup $\)** window, then the ESR main bank selected in the **\($ N\_3010531 ESR Setup $\)** window will be printed.|  
    |**LogInteraction**|Specify if the interactions that you have with your contacts will be logged.|  
    |**\($ B\_3010532\_F\_1\_1150002 ESR System $\)**|Select the ESR system through which you can send new ESR coupons to customers. To use the ESR system that is used by the bank that you have specified in **\($ B\_3010532\_F\_1\_1150003 ESR Bank $\)** field, select **Based on ESR Bank**.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
     You can also reprint the sales invoice ESR report or sales ESR coupon report.  
  
## See Also  
 [Swiss Electronic Payments Using ESR](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-esr.md)   
 [How to: Import ESR Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-import-esr-payments.md)   
 [\($ T\_3010531 ESR Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010531-esr-setup-$-.md)   
 [\($ T\_78 Printer Selection $\)](assetId:///e7c3bf24-9d03-418b-9826-d6125b34a516)