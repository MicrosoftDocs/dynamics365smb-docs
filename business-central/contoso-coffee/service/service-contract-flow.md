---
title: Walkthrough of service contracts for service items
description: This article guides you through some scenarios for service items and contracts.
author: brentholtorf
ms.author: bholtorf
ms.topic: how-to
ms.date: 08/26/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Walkthrough of service contracts for service items

This walkthrough demonstrates several core processes:

- Create service items through sales
- Create and invoice a service contract
- Create a service order for a service contract
- Assign a resource based on skill and zone
- Complete a time entry for the service order
- Post and invoice the contract service order

## Create service items

### Scenario  

Susan, the order processor, posts a sales order selling an item that is configured to generate a service item.  

### Steps

1. Check that **Item** has **Service Item Group** selected.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
    2. Select the item *S-100* and open it.
    3. Check the value in the **Service Item Group** field.

2. Post the **Sales Order** to create the service item for the customer.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Select the order for customer 10000. The external document number is *SVC-1*.
    3. Choose the **Post** action to ship the item to the customer.

### Results

A service item is created for customer 10000.

## Invoice a service contract

### Scenario

Charles, the service manager, creates a service contract to invoice for regular maintenance visits.

1. Create the **Service Contract** for the new service item.
    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.
    2. Choose the **New** action.  
    3. In the confirmation dialog, choose **Yes** to create contract using template. 
    4. Select **Non-Prepaid Contract - Monthly**.
    5. On the Service FastTab, in the **Service Order Type** field, enter **MAINTEN**.
    6. On the lines, enter the following information:

    |Service Item No.|Line Value|  
    |----------------|----------|  
    |SV000001|6000|

    7. Choose the **Sign Contract** action and confirm the signing.
    8. Choose **Yes** to confirm creation of a service invoice. You receive a confirmation message with the service invoice number.

3. Post the service invoice.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Invoices**, and then choose the related link.
   2. Locate the service invoice and choose the **Post** action.

### Results

- A signed service contract is created, with ledger entries
- A posted service invoice is created

## Create a service order for a service contract and assign resources

### Scenario

Charles, the service manager, creates service orders for regular maintenance orders under a service contract, and then reviews the Dispatch Board page to assign them.

### Steps

1. Run the service orders that fulfill the obligations of active service contracts.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Contract Service Orders**, and then choose the related link.
   2. Enter *01* in the **Starting Date** field. It will be transformed into begining of the month based on work date. 
   3. Enter the ending date of the month in the **Ending Date** field.
   4. Choose **OK** to confirm creation of service orders. You receive a confirmation message with the number of created service orders.

2. Review the orders awaiting assignment on the **Dispatch Board** page.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.
   2. The Dispatch Board page shows all open service orders, along with the **No. of Allocations** to show whether the service orders are assigned to a resource.
   3. Choose the **Show Documents** action to open a service order. The **Service Item Lines** FactBox shows which resources are skilled at working with this item.

3. Assign a resource to the service order.

   1. From the service order, choose the line action **Resource Allocations**.
   2. Enter the following information for the resource allocation.

    |Service Item No.|Resource No.|Allocation Date|Allocated Hours|
    |----------------|------------|---------------|---------------|  
    |SV000001|RESOURCE1|Work date.</br> A fast way to enter the work date is to enter some or all of the word *work* in the language in which you use [!INCLUDE [prod_short](../../includes/prod_short.md)]. For example, in English, you can enter *w*. |1|

    3. The status of the allocation changes to **Active**.
    4. Refresh the Dispatch Board page to show that the **No of Allocations** changed from **0** to **1** for the service order.

### Results

- Service orders are created for the service contracts
- Service orders are allocated to a resource to complete the work

## Complete the time entry for the service order and post the service order

### Scenario

The service technician registers their time directly against the service order, then marks the order as finished.

### Steps

1. Locate the service order, and enter the time on the service line.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.
   2. Locate the service order that you want to enter time for.
   3. Choose the line action **Service Line**.
   4. Enter the following information:

    |Type|No.|Quantity|Qty.to Consume|
    |----|---|--------|--------|  
    |Resource|RESOURCE1|2|2|

2. On the service order, post the consumption.

   1. Choose the **Post** action to complete the service order, select the **Ship and Consume** action, and then choose the **OK** button.

### Results

- Service ledger entries are created and associated with the service item, service contract, and resource.

## See also

[Introduction to Contoso Coffee Demo Data](../../contoso-coffee/contoso-coffee-intro.md)  
[Service](../../service-service.md)
