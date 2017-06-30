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
# How to: Set Up Physical Inventory Counting Periods
A physical inventory is typically taken at some recurring interval, for example monthly, quarterly, or annually. You can set up whatever inventory counting periods necessary.  
  
 You set up the inventory counting periods that you want to use and then assign one to each SKU or item. When you perform a physical inventory and use the function **Calculate Counting Period** in the warehouse physical inventory journal or in the physical inventory journal, lines for the bins containing these items or SKUs are created automatically.  
  
### To set up counting periods  
  
1.  In the **Search** box, enter **Phys. Invt. Counting Periods**, and then choose the related link.  
  
2.  Fill in the **Code** field with a short descriptive code for the counting period.  
  
3.  Enter a short description in the **Description** field, if you wish.  
  
4.  Fill in the **Count Frequency per Year** field with the number of times you want to perform a physical inventory each year.  
  
### To assign a counting period to an item or stockkeeping unit  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select the item to which you want to assign a counting period.  
  
3.  On the **Warehouse** FastTab, select the **Phys Invt Counting Period Code** field, and select the appropriate counting period.  
  
     Choose the **Yes** button to change the code and calculate the first counting period for the item. The next time you choose to calculate a counting period in the warehouse physical inventory journal, the item appears as a line in the **Phys. Invt. Item Selection** window. You can now begin to count the item on a periodic basis.  
  
## See Also  
 [How to: Perform a Physical Inventory](../how-to-perform-a-physical-inventory.md)   
 Phys. Invt. Counting Periods