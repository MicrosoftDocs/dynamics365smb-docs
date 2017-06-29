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
# How to: Create the TORG-1 Report for Acceptance of Goods
The TORG\-1 report is used for the registration of incoming goods. This report lists receipts with quantity, quality, mass, and package contents according to the terms of an agreement. Depending on your setup, the batch job can be run when you choose the **Print** button in document windows such as the **Purchase Order** window.  
  
### To create the TORG\-1 report  
  
1.  In the **Search** box, enter **Item Receipts Act TORG\-1**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_14918\_F\_1\_1210002 Show Actual Quantity $\)**|Specifies if the TORG\-1 report must include actual quantities for received items.|  
    |**\($ B\_14918\_F\_1\_1210000 Order No. $\)**|Specifies the document number.|  
    |**\($ B\_14918\_F\_1\_1210005 Order Date $\)**|Specifies the document date.|  
    |**\($ B\_14918\_F\_1\_1210007 Operation Type $\)**|Specifies the report type.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Inventory Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/inventory-setup.md)   
 Item Report TORG\-29   
 Items Receipt Act TORG\-1   
 Receipt Deviations TORG\-2