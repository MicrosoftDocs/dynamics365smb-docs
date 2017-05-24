---
title: "How to: Set Up Recurring Groups"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "recurring groups"
ms.assetid: e496b996-f61d-4c25-b223-fe14e1482ae5
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Set Up Recurring Groups
The **\($ T\_36\_15000300 Recurring Group Code $\)** field in the **\($ N\_507 Blanket Sales Order $\)** window defines date formulas that can be used both as a template and to create sales orders based on date intervals. You must set up recurring groups before you can set up recurring orders.  
  
### To set up recurring groups  
  
1.  In the **Search** box, enter **Recurring Groups**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_15000300\_1 Code $\)**|Enter a code to identify the recurring group.|  
    |**\($ T\_15000300\_2 Description $\)**|Enter a description for the recurring group.|  
    |**\($ T\_15000300\_3 Date formula $\)**|Enter a date formula to calculate the time interval between orders.|  
    |**\($ T\_15000300\_4 Create only the latest $\)**|Select if you want only the latest recurring order created if the recurring group interval created by the **\($ T\_15000300\_3 Date formula $\)** has been exceeded.<br /><br /> If the order date on the blanket sales order has exceeded more than one interval period, selecting this check box prevents how all orders are created, and will only create the latest order.|  
    |**\($ T\_15000300\_5 Starting date $\)**|Enter the first date of the recurring group.|  
    |**\($ T\_15000300\_6 Closing date $\)**|Enter the last date of the recurring group.|  
  
4.  On the **Update** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_15000300\_20 Update Document Date $\)**|Select one of the following options to update the document date:<br /><br /> -   **Posting Date** \- The document date is calculated using the posting date and the date formula specified in the **\($ T\_15000300\_22 Document Date Formula $\)** field.<br />-   **Processing Date** \- The document date is calculated using the processing date and the date formula specified in the **\($ T\_15000300\_22 Document Date Formula $\)** field.|  
    |**\($ T\_15000300\_22 Document Date Formula $\)**|Enter a date formula to calculate the document date on the order.|  
    |**\($ T\_15000300\_24 Delivery Date Formula $\)**|Enter a date formula to calculate the delivery date on the order.|  
    |**\($ T\_15000300\_25 Update Price $\)**|Select one of the following options for updating prices on new orders:<br /><br /> -   **Fixed** \- The price used on a new order is the same price that is specified in the blanket order.<br />-   **Recalculate** \- The price on a new order is recalculated to reflect the current price for the customer.<br />-   **Reset** \- The price on a new order is cleared to specify a new price.|  
    |**\($ T\_15000300\_26 Update Number $\)**|Select one of the following options to manage the quantity specified on the original order:<br /><br /> -   **Constant** \- The quantity on the blanket order remains unchanged. This enables you to make orders indefinitely from the blanket order.<br />-   **Reduce** \- The quantity on the blanket order is reduced with the quantity that is specified on the new order. The recurring order processing stops when the quantity specified on the blanket order is used on new orders.|  
    |**\($ T\_15000300\_27 Reset Delivery $\)**|Select to reset the delivery options for the recurring group.|  
  
5.  Choose the **OK** button.  
  
## See Also  
 [How to: Enter Dates and Times](../../WorkingWithDynamics/how-to-enter-dates-and-times.md)   
 [Recurring Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/recurring-orders.md)   
 [How to: Set Up Recurring Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-recurring-orders.md)   
 [How to: Create Recurring Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-recurring-orders.md)