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
# How to: Make General Changes in Direct Unit Cost
If you need to change the direct unit cost for several items, you can use the **Adjust Item Costs\/Prices** batch job.  
  
 The batch job changes the contents in the **Unit Price** field on the item card. The batch job changes the content of the field in the same way for all items or selected items. The batch job multiplies the value in the field by an adjustment factor that you specify.  
  
### To make a general change in direct unit cost  
  
1.  In the **Search** box, enter **Adjust Item Costs\/Prices**, and then choose the related link.  
  
2.  On the **Options** FastTab, in the **Adjust Field** field, specify which item or SKU card field you want to adjust.  
  
3.  In the **Adjustment Factor** field, specify the factor by which the value will be adjusted. For example, enter **1.5** to increase the value by 50%.  
  
4.  On the **Item** FastTab, set filters to specify, for example, which items to process with the batch job.  
  
5.  Choose the **OK** button.  
  
## See Also  
 Adjust Item Costs-Prices