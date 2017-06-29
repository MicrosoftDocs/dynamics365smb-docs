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
# How to: Print ESR Invoices
You can print an Einzahlungsschein mit Referenznummer \(ESR\) payment slip in the following ways:  
  
-   As part of the sales invoice ESR.  
  
-   As a separate document called an ESR coupon.  
  
 The sales invoice ESR report corresponds with the sales invoice that is accompanied by an additional ESR coupon. By using the sales ESR coupon report, you can print the blue deposit slip.  
  
> [!NOTE]  
>  You must select a printer and select settings during the ESR payment module installation to print the deposit slip correctly. For more information, see the Printer Selection table.  
  
 The following procedure describes how to print ESR sales invoices, but the same steps also apply for printing ESR coupons.  
  
### To print ESR invoices  
  
1.  In the **Search** box, enter **Invoice ESR**, and then choose the related link.  
  
2.  In the **Sales Invoice ESR** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_3010532\_F\_1\_1150006 No. of copies $\)**|Enter the required number of report copies.|  
    |**\($ B\_3010532\_F\_1\_1150003 ESR Bank $\)**|Select the ESR bank code that is to be printed in the report.<br /><br /> If the value in this field is \<Blank\> and the ESR payment method code is not defined in the **ESR Setup** window, then the ESR main bank selected in the **ESR Setup** window will be printed.|  
    |**LogInteraction**|Specify if the interactions that you have with your contacts will be logged.|  
    |**\($ B\_3010532\_F\_1\_1150002 ESR System $\)**|Select the ESR system through which you can send new ESR coupons to customers. To use the ESR system that is used by the bank that you have specified in **\($ B\_3010532\_F\_1\_1150003 ESR Bank $\)** field, select **Based on ESR Bank**.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
     You can also reprint the sales invoice ESR report or sales ESR coupon report.  
  
## See Also  
 [Swiss Electronic Payments Using ESR](../FullExperience/swiss-electronic-payments-using-esr.md)   
 [How to: Import ESR Payments](../FullExperience/how-to-import-esr-payments.md)   
 ESR Setup   
 Printer Selection