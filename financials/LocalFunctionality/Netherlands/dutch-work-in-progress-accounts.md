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
# Dutch Work in Progress Accounts
When there is a change in the number of items in inventory, you can determine whether this is due to sales or inventory replenishment by tracking postings made to the relevant Work in Progress \(WIP\) account.  
  
 The financial statements must accurately reflect the financial position of the company. Management reports reflect the changes in the value of the inventory due to sales or inventory replenishment.  
  
## Posting Work In Progress  
 In the Netherlands, work in progress posting depends on whether an inventory item is part of a bill of material \(BOM\).  
  
-   For items that are part of a BOM, you must post the work in progress to the WIP account that is assigned to the finished product.  
  
-   For items that are not part of a BOM, you must post the work in progress to the WIP account that is assigned to the individual item.  
  
 For example, if a bicycle wheel is produced for stock, assign the WIP account to the wheel. If the bicycle wheel is produced as a BOM component for a bicycle, assign the WIP account to the bicycle.  
  
## See Also  
 [Netherlands Local Functionality](../netherlands-local-functionality.md)