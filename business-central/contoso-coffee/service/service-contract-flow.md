---
title: Walkthrough of Service Contracts for Service Items
description: Use Contoso Coffee demo data to create and invoice a service contract, assign a skilled resource, and record and post service work.
author: brentholtorf
ms.author: bholtorf
ms.topic: how-to
ms.date: 11/12/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Walkthrough of service contracts for service items

This walkthrough demonstrates several core processes:

- Create service items through sales
- Create and invoice a service contract
- Create a service order for a service contract
- Assign a resource based on skill
- Complete a time entry for the service order
- Post consumption for the contract service order

## Prerequisites

On the **Contoso Demo Tool** page, generate all data for the **Service** module. This walkthrough uses the default module configuration and a prepaid monthly contract template so you can invoice the contract before completing the service work. Learn more in [Introduction to Contoso Coffee demo data](../contoso-coffee-intro.md).

## Create service items

### Scenario  

Susan, the order processor, posts a sales order selling an item that is configured to generate a service item.  

### Steps

1. Check that **Item** has **Service Item Group** selected.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Items**, and then choose the related link.
    1. Select the item *S-100* and open it.
    1. Check that the **Service Item Group** field is set to **SERVICE**.

1. Post the **Sales Order** to create the service item for the customer.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Orders**, and then choose the related link.
    1. Select the order for customer 10000. The external document number is *SVC-1*.
    1. Choose the **Post** action to ship the item to the customer.

### Results

A service item is created for customer 10000.

## Invoice a service contract

### Scenario

Charles, the service manager, creates a service contract to invoice for regular maintenance visits.

1. Create the **Service Contract** for the new service item.
    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Contracts**, and then choose the related link.
    1. Choose the **New** action.
    1. In the confirmation dialog, choose **Yes** to create contract using template.
    1. Select **Prepaid Contract - Monthly**.
    1. In the **Customer No.** field, enter **10000**.
    1. On the Service FastTab, in the **Service Order Type** field, enter **MAINTEN**.
    1. On the lines, select the service item created when you posted the sales order, and enter the following information:

    |Service Item No.|Line Value|  
    |----------------|----------|  
    |The service item created for customer 10000|6000|

    1. Choose the **Sign Contract** action and confirm the signing.
    1. Choose **Yes** to confirm creation of a service invoice. You receive a confirmation message with the service invoice number.

1. Post the service invoice.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Invoices**, and then choose the related link.
   1. Locate the service invoice and choose the **Post** action.

### Results

- A signed service contract is created, with ledger entries
- A posted service invoice is created

## Create a service order for a service contract and assign resources

### Scenario

Charles, the service manager, creates service orders for regular maintenance orders under a service contract, and then reviews the Dispatch Board page to assign them.

### Steps

1. Run the service orders that fulfill the obligations of active service contracts.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Create Contract Service Orders**, and then choose the related link.
   1. Enter *01* in the **Starting Date** field. It will be transformed into beginning of the month based on work date.
   1. Enter the ending date of the month in the **Ending Date** field.
   1. Choose **OK** to confirm creation of service orders. You receive a confirmation message with the number of created service orders.

1. Review the orders awaiting assignment on the **Dispatch Board** page.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Dispatch Board**, and then choose the related link.
   1. The Dispatch Board page shows all open service orders, along with the **No. of Allocations** to show whether the service orders are assigned to a resource.
   1. Choose the **Show Documents** action to open a service order. The **Service Item Lines** FactBox shows which resources are skilled at working with this item.

1. Assign a resource to the service order.

   1. From the service order, choose the line action **Resource Allocations**.
   1. Enter the following information for the resource allocation. **RESOURCE2** has the **PLUMBING** skill required by item **S-100**.

    |Service Item No.|Resource No.|Allocation Date|Allocated Hours|
    |----------------|------------|---------------|---------------|  
    |The service item created for customer 10000|RESOURCE2|Work date.<br> A fast way to enter the work date is to enter some or all of the word *work* in the language in which you use [!INCLUDE [prod_short](../../includes/prod_short.md)]. For example, in English, you can enter *w*. |1|

   1. The status of the allocation changes to **Active**.
   1. Refresh the Dispatch Board page to show that the **No of Allocations** changed from **0** to **1** for the service order.

### Results

- Service orders are created for the service contracts
- Service orders are allocated to a resource to complete the work

## Complete the time entry for the service order and post the service order

### Scenario

The service technician registers their time directly against the service order, then marks the order as finished.

### Steps

1. Locate the service order, and enter the time on the service line.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Orders**, and then choose the related link.
   1. Locate the service order that you want to enter time for.
   1. Choose the line action **Service Line**.
   1. Enter the following information:

    |Type|No.|Quantity|Qty.to Consume|
    |----|---|--------|--------|  
    |Resource|RESOURCE2|2|2|

   1. Return to the service order. On the service item line, set **Repair Status Code** to **FINISHED**.

1. On the service order, post the consumption.

   1. Choose the **Post** action to complete the service order, select the **Ship and Consume** action, and then choose the **OK** button.

### Results

- Service ledger entries are created and associated with the service item, service contract, and resource.

## Related information

[Introduction to Contoso Coffee Demo Data](../../contoso-coffee/contoso-coffee-intro.md)  
[Service](../../service-service.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
