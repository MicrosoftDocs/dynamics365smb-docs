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
# Unit Cost Calculation
As a rule, the value in the Unit Cost field on the item card is based on the standard cost for items with costing method standard. For items with all other costing methods, it is based on the calculation of the inventory available \(invoiced costs and expected costs\) divided by the quantity on hand.  
  
 How the contents of the **Costing Method** field influence the unit cost calculation for purchases and sales is described in more detail in the following sections.  
  
## Unit Cost Calculation for Purchases  
 When you purchase items, the value in the **Last Direct Cost** field on the item card is copied to the Direct Unit Cost field on a purchase line or to the Unit Amount line on an item journal line.  
  
 What you select in the **Costing Method** field influences how FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> calculates the contents of the **Unit Cost** field on the lines.  
  
### Costing Method FIFO, LIFO, Specific, or Average  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] calculates the contents of the Unit Cost \(LCY\)%20$\).md) field on the purchase line or the contents of the Unit Cost field on the item journal line according to the following formula:  
  
 Unit Cost \(LCY\) \= \(Direct Unit Cost – \(Discount Amount\/ Quantity\)\) \* \(1 \+ Indirect Cost %" \/ 100\)\) \+ Overhead Rate  
  
### Costing Method Standard  
 The **Unit Cost \(LCY\)** field on the purchase line or the **Unit Cost** field is filled on the item journal line by copying the value in the **Unit Cost** field on the item card. By using costing method set as Standard, this is always based on the standard cost.  
  
 When you post the purchase, the unit cost from the purchase line or item journal line is copied to the purchase item invoice entry, and it can be seen on the entry list for the item.  
  
### All Costing Methods  
 The unit cost from the source document line is used to calculate the contents of the Cost Amount \(Actual\)%20$\).md) field, or if applicable, the Cost Amount \(Expected\)%20$\).md) field that relates to this item entry, regardless of the costing method of the item.  
  
## Unit Cost Calculation for Sales  
 When you sell items, the unit cost is copied from the Unit Cost field on the item card to the sales line or the item journal line.  
  
 When you post, the unit cost is copied to the sales invoice item entry, and it can be seen on the entry list for the item. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] uses the unit cost from the source document line to calculate the contents of the Cost Amount \(Actual\)%20$\).md) field, or if applicable, the Cost Amount \(Expected\)%20$\).md) field in the value entry related to this item entry.  
  
## See Also  
 Costing Method   
 Value Entry   
 [Average Cost](../Finance/average-cost.md)