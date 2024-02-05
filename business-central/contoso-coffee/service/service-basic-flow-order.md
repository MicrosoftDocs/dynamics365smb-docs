---
title: Walkthrough of service orders for service items
description: This article guides you through several core processes that involve service orders and items.
author: andreipa
ms.author: andreipa
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 05/31/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Walkthrough of service orders for service items

This walkthrough demonstrates several core processes:

- Create an ad hoc Service Order and register repair of the Item
- Provide a Loaner Item to customer for a time of repair
- Post and Invoice the Service Order
    
## Creating a service order

### Scenario  

Charles, the service manager, creates a Service Order for a repair scenario, lend a Loaner to the customer for time of repair.

### Steps

1. Create the Service Order manually for the Item that requires repair.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**
   2. Choose the **New** action.
   3. Enter **10000** into the Customer No. field
   4. Select **REPAIR** for the **Service Order Type** field.
   5. In the Lines, select **S-100** as the **Item No.**.
2. Optionally
   1. Choose the Line action **Troubleshooting** to check possible solutions.
   2. Choose the Line action **Fault/Resol. Codes Relationships**
   3. Select *NOISE* as **Symptom Code**
   4. Select *5-2 Loud noise during brewing* as **Faul Code** and close page. Fault code, resolution codes are updated in lines.
3. Lend a replacement while item is being repaired
   1. In the Lines, select **LOANER1** as the Loaner No. Confirm the issuance of the Loaner by selecting **Yes** to lend out the Loaner. 
   2. Choose the Functions action **Get Std. Service Codes**, select standard code associated with service group and select **Ok**.
   
### Results

- A Service Order is created for the Item
- The Service Order's Service Document Log shows the Loaner activities.
- The Loaner has a Ledger Entry to reflect the lending.
   

## Register performed work, mark loaner as returned.

### Scenario  

The service technician marks loaner as returned, registers performed work.

### Steps

1. Locate the Service task and register time 
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
   2. Locate the Service Order to enter time for.
   3. Choose  the **Item Worksheet** action.
   4. Enter the following information

    |Type|No.|Quantity|
    |----|---|--------|  
    |Item|SER102|2|

   4. Select *FINISHED* in the **Repair Status Code** field
    
2. Mark loaner as returned
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Loaners**, and then choose the related link.
   2. Locate the loaner to mark as returned.
   3. Choose the **Receive** action 
   4. Confirm the return of the Loaner by selecting **Yes** to return the Loaner.
      
### Results

- The service order's **Service Document Log** shows the Loaner activities.
- The Loaner has a Ledger Entry to reflect the receipt.


### Scenario  

Charles, the service manager, post the finished service order.

1. Locate the Service Order 
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.
   2. Locate the Service Order you want to post.

2. On the Service Order, Post the Invoice
   1. Choose the **Post** action to complete the Service Order, select the **Ship and Invoice** action, and then choose the **OK** button.
   2. Confirm the opening of the posted invoice by selecting **Yes**. 
### Results

- the **Posted Service Invoice** is created.
- the **Service Ledger Entries** associated with the Item and Resource are created

## See also
[Walkthrough of Service Contracts for Service Items](service-contract-flow.md)  
[Service](../../service-service.md)
