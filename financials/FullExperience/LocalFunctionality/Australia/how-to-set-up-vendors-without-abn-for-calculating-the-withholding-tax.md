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
# How to: Set Up Vendors Without ABN for Calculating the Withholding Tax
Withholding Tax \(WHT\) is calculated for local vendors who do not have an Australian Business Number \(ABN\), as required by tax law.  
  
### To set up vendors without ABN for calculating the withholding tax  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Choose the required vendor, and then, on the **Home** tab, choose **Edit**.  
  
3.  In the **Vendor Card** window, on the **Registration** FastTab, the **ABN** field and **Foreign Vend** field must be empty.  
  
4.  Choose the **OK** button.  
  
    > [!NOTE]  
    >  The WHT percentage is automatically withheld in accordance with what was specified in the **WHT Posting Setup** window. The WHT certificate is produced for submission to the vendor. For more information, see [Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/withholding-tax.md).  
  
## See Also  
 [Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/withholding-tax.md)   
 [How to: Set Up Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-set-up-withholding-tax.md)