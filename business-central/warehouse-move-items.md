---
title: Move Items
description: Learn about moving items between bins in your warehouse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: concept-article
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.form: 7315, 7349, 7351, 7382, 7384, 7386, 7387, 7399, 7400, 9314, 9330, 9345
---
# Moving Items

You can move items in your warehouse in different ways, depending on how you've configured your warehouse. The complexity can vary:

* Small warehouses might use basic warehouse configurations to handle orders individually, in a single or multiple steps.
* Large warehouses might use advanced configurations where all warehouse activities are coordinated by a directed workflow. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

Items may need to be moved between bins, for example, due to internal operations:

* A production order needs components delivered, or its finished items put away.
* A warehouse manager wants to optimize space.
* Unplanned movements to and from operations.
* Replenish picking bins or shop floor bins.
* Update bin contents.

Counting, adjusting, and reclassifying items can involve warehouse tasks that must be performed on warehouse entries before they can be synchronized with item ledger entries. Learn more at [Count, Adjust, and Reclassify Inventory](inventory-how-count-adjust-reclassify.md).  

 The following table describes a sequence of tasks, with links to the articles that describe them.

|**To**|**See**|  
|------------|-------------|  
|Moving items between locations|[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)|
|Move items between bins in basic warehouse configurations at any time and without source documents.|[Move Items in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)|
|Use the warehouse movement worksheet, internal pick and put-away to move items in advanced warehouse configurations with directed pick and put away.|[Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md)|  
|Restructure your warehouse with new bin codes and new bin characteristics and potentially move them around.|[Restructure Warehouses](warehouse-how-to-restructure-warehouses.md)|  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
