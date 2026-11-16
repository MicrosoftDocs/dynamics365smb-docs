---
title: Walkthrough of Service Orders for Service Items
description: Use Contoso Coffee demo data to create a service order, lend and receive a loaner, record repair work, and post and invoice the service order.
author: andreipa
ms.author: andreipa
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 11/12/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Walkthrough of service orders for service items

This walkthrough demonstrates several core processes:

- Create a service order and register the repair of an item.
- Provide a loaner item to the customer while the repair is underway.
- Post and invoice a service order.

## Prerequisites

On the **Contoso Demo Tool** page, generate all data for the **Service** module. This walkthrough uses the default module configuration. Learn more in [Introduction to Contoso Coffee demo data](../contoso-coffee-intro.md).

## Scenario: create a service order

Charles, the service manager, creates a service order for a repair, and lends a loaner item to the customer.

### Steps

1. Create a service order manually for the item that requires repair.
   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Orders**, and then choose the related link.
   1. Choose the **New** action.
   1. In the **Customer No.** field, enter **10000**.
   1. In the **Service Order Type** field, choose **REPAIR**.
   1. On the **Lines** FastTab, in the **Item No.** field, choose **S-100**.
1. Optional steps:
   1. Choose the **Troubleshooting** action on the **Lines** FastTab to check for possible solutions.
   1. Choose the **Fault/Resol. Codes Relationships** action on the **Lines** FastTab.
   1. In the **Symptom Code** field, choose **NOISE**.
   1. In the **Fault Code** field, choose **5-2 Loud noise during brewing**, and then close the page. The fault code and resolution codes update on the lines.
1. Lend a loaner item while item is being repaired.
   1. On the lines, select **LOANER** as the **Loaner No.** To confirm the loan, choose **Yes**.
   1. Choose the **Get Std. Service Codes** action, select **LOANER**, and then choose **OK**.
1. Close service order page and return to the Role Center.

### Results

- A service order is created for the item.
- The Service Document Log page shows the loan.
- The loaner item has a ledger entry to record the loan.

## Scenario: register the work, and mark the loaner item as returned

The service technician marks the loaner item as returned, and registers the work they did.

### Steps

1. Find the service task and register the time spent.
   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Tasks**, and then choose the related link.
   1. Find the service order to enter time for.
   1. Choose the **Item Worksheet** action.
   1. Enter the information as described in the following table.

    |Type|No.|Quantity|
    |----|---|--------|  
    |Item|SER102|2|

   1. In the **Repair Status Code** field, choose **FINISHED**.
   1. Close the service item worksheet and service tasks pages and return to the Role Center.

1. Mark the loaner item as returned.
   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Loaners**, and then choose the related link.
   1. Find the loaner item that was returned.
   1. Choose the **Receive** action.
   1. Confirm the return of the loaner item by selecting **Yes**.
   1. Close the **Loaners** page and return to the Role Center.

### Results

- The service order's **Service Document Log** page shows the loan.
- The loaner item has a ledger entry to record its receipt.

## Scenario: post and invoice the service order

Charles, the service manager, posts the finished service order.

1. Open the service order.
   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Orders**, and then choose the related link.
   1. Find the service order you want to post.

1. On the **Service Order** page, post the invoice.
   1. Choose the **Post** action to complete the service order, select the **Ship and Invoice** action, and then choose the **OK** button.
   1. To confirm the opening of the posted invoice, choose **Yes**.

### Results

- A **Posted Service Invoice** is created.
- Service ledger entries are created for the invoiced service lines.

## Related information

[Walkthrough of Service Contracts for Service Items](service-contract-flow.md)  
[Service](../../service-service.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
