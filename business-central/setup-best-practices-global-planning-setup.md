---
title: Best practices for global planning setup | Microsoft Docs
description: The Planning FastTab in the Manufacturing Setup page contains several fields that define global rules for supply planning.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: best-practice
ms.date: 09/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Setup Best Practices: Global Planning Setup

The **Planning** FastTab on the **Inventory Setup** page contains several fields that define global rules for supply planning.  

The following table provides best practices on how to set up selected global planning parameter fields.  

| Setup field | Best practice |
|-----------------|-------------------|
|Use Forecast on Locations|Select if you have forecasts for specific locations.|
|Use Forecast on Variants| Select if you have items with variants and want to specify forecast for each variant individually|
|Blank Overflow Level|Use only if you want to allow all or some of your items to overflow the reorder point.|
|Default Dampener Period|Set between 1D and 5D.<br/><br/> If you're new to planning in [!INCLUDE[prod_short](includes/prod_short.md)], set a longer period. When you're more familiar with the different reasons for action messages, shorten the dampener period to allow more change suggestions.|  
|Default Dampener Quantity %|Set between 5 and 20 percent of the item’s lot size.|

The **Planning** FastTab on the **Manufacturing Setup** page also contains several fields that define global rules for supply planning.  

The following table provides best practices on how to set up selected global planning parameter fields.

|Setup field|Best practice|
|-----------------|-------------------|
|Components at Location|If items aren't defined as SKUs, select the location code of your main warehouse. This selection also applies if you only use the requisition worksheet.|  

## Related information  

[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Set Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
