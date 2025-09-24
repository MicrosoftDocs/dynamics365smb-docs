---
title: How to work with responsibility centers
description: Responsibility center as administrative centers help companies set up user-specific views of sales and purchase documents related exclusively to each center.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.forms: 5714, 5715
ms.date: 05/16/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Work with responsibility centers

Responsibility centers provide the ability to handle administrative centers. A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center. Examples of responsibility centers are a sales office, a purchasing department for several locations, and a plant planning office. For example, companies can set up user-specific views of sales and purchase documents related to a particular responsibility center.  

Using multiple locations together with responsibility centers provides the ability to manage business operations in flexible, optimal ways.

Multiple locations allow companies to manage their inventory in multiple locations using one database. Two concepts, locations and stockkeeping units, are the cornerstones of this granule. A location is defined as a place that handles physical placement and quantities of items. The concept is broad enough to include locations such as plants or production facilities and distribution centers, warehouses, showrooms, and service vehicles. A stockkeeping unit is defined as an item at a specific location and/or as a variant. Using stockkeeping units, companies with multiple locations can add replenishment information, addresses, and some financial posting information at the location level. As a result, they can replenish variants of the same item for each location and order items based on location-specific replenishment information.  

## To set up a responsibility center

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Responsibility Centers**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    If you're using responsibility centers to administer your company, it can be useful to have a default responsibility center.
4. [!INCLUDE[open-search](includes/open-search.md)], enter **Company Information**, and then choose the related link.
5. On the **Shipping** FastTab, in the **Responsibility Center** field, enter a responsibility center code.

This code is used on all purchase, sales, or service documents, if the user, customer, or vendor has no default responsibility center. On sales, purchase, or service documents, you can enter another responsibility center than the default.

> [!NOTE]  
> When you enter a responsibility center code on a document, it affects the address, dimensions, and prices on the document.  

## To assign responsibility centers to users

You can set up users so that [!INCLUDE [prod_short](includes/prod_short.md)] retrieves only the documents relevant for their particular work areas. Users are associated with one responsibility center and work only with documents related to specific application areas at that particular center.  

To set this up, you assign responsibility centers to users in three functional areas: Purchases, Sales, and Service Management.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **User Setup**, and then choose the related link.  
2. On the **User Setup** page, select the user you want to assign a responsibility center to. If the user not is on the list, you must enter a user ID in the **User ID** field.  
3. In the **Sales Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to sales.  
4. In the **Purchase Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to purchasing.  
5. In the **Service Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to service management.  

> [!NOTE]  
> Users can view only those posted documents that related to their own responsibility center. However, they can view all ledger entries and navigate to other posted documents from the ledger entries.

## Related information

[Setting Up Inventory](inventory-setup-inventory.md)    
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)    
[Inventory](inventory-manage-inventory.md)    
[Warehouse Management Overview](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    
[Define an invoice posting policy for users](admin-setup-invoice-posting-policy.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
