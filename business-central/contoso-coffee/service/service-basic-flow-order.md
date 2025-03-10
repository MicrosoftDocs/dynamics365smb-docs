---
title: Walkthrough of service orders for service items
description: This article guides you through several core processes that involve service orders and items.
author: andreipa
ms.author: andreipa
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/18/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Walkthrough of service orders for service items

This walkthrough demonstrates several core processes:

- Create a service order and register the repair of an item.
- Provide a loaner item to the customer while the repair is underway.
- Post and invoice a service order.

## Scenario: create a service order

Charles, the service manager, creates a service order for a repair, and lends a loaner item to the customer.

### Steps

1. Create a service order manually for the item that requires repair.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, and enter **Service Orders**.
   2. Choose the **New** action.
   3. In the **Customer No.** field, enter **10000**.
   4. In the **Service Order Type** field, choose **REPAIR**.
   5. On the **Lines** FastTab, in the **Item No.** field, choose **S-100**.
2. Optional steps:
   1. Choose the **Troubleshooting** action on the **Lines** FastTab to check for possible solutions.
   2. Choose the **Fault/Resol. Codes Relationships** action on the **Lines** FastTab.
   3. In the **Symptom Code** field, choose **NOISE**.
   4. In the **Fault Code** field, choose **5-2 Loud noise during brewing**, and then close the page. The fault code and resolution codes update on the lines.
3. Lend a loaner item while item is being repaired.
   1. On the lines, select **LOANER1** as the **Loaner No.** To confirm the loan, choose **Yes**.
   2. Choose the **Get Std. Service Codes** action, select standard code associated with the service group, and then choose **OK**.
4. Close service order page and return to the Role Center.

### Results

- A service order is created for the item.
- The Service Document Log page shows the loan.
- The loaner item has a ledger entry to record the loan.

## Scenario: register the work, and mark the loaner item as returned

The service technician marks the loaner item as returned, and registers the work they did.

### Steps

1. Find the service task and register the time spent.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
   2. Find the service order to enter time for.
   3. Choose the **Item Worksheet** action.
   4. Enter the information as described in the following table.

    |Type|No.|Quantity|
    |----|---|--------|  
    |Item|SER102|2|

   5. In the **Repair Status Code** field, choose **FINISHED**.
   6. Close the service item worksheet and service tasks pages and return to the Role Center.

2. Mark the loaner item as returned.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Loaners**, and then choose the related link.
   2. Find the loaner item that was returned.
   3. Choose the **Receive** action.
   4. Confirm the return of the loaner item by selecting **Yes**.
   5. Close the **Loaners** page and return to the Role Center.

### Results

- The service order's **Service Document Log** page shows the loan.
- The loaner item has a ledger entry to record its receipt.

## Scenario: post and invoice the service order

Charles, the service manager, posts the finished service order.

1. Open the service order.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.
   2. Find the service order you want to post.

2. On the **Service Order** page, post the invoice.
   1. Choose the **Post** action to complete the service order, select the **Ship and Invoice** action, and then choose the **OK** button.
   2. To confirm the opening of the posted invoice, choose **Yes**.

### Results

- A **Posted Service Invoice** is created.
- Service ledger entries are created for the item and resource.

## Related information

[Walkthrough of Service Contracts for Service Items](service-contract-flow.md)  
[Service](../../service-service.md)
