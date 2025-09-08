---
title: Set Up Warehouse Employees
description: Each user who performs warehouse activities must be set up as a warehouse employee assigned to one default location and potentially more non-default locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 09/25/2023
ms.custom: bap-template
ms.search.form: 7328, 7348
ms.service: dynamics-365-business-central
---
# Set Up Warehouse Employees

You must set up each user who performs warehouse activities as a warehouse employee and assign them to a default location. [!INCLUDE [prod_short](includes/prod_short.md)] filters warehouse activities to the employee's default location. They can only perform the warehouse activities at the location. You can also assign a user to other locations. They can access but not perform activities at those locations.

## To set up warehouse employees  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Warehouse Employees**, and then choose the related link.  
2. Choose the **New** action.  
3. Select the **User ID** field, and then select the user to be added as a warehouse employee. Choose the **OK** button.  
4. In the **Location Code** field, enter the code of the location where the user will be working.  
5. Turn on the **Default** toggle to specify that this is the only location where the employee can perform warehouse activities.  
6. Repeat these steps to assign other employees to locations or assign other locations to existing warehouse employees.  

> [!TIP]
> You can also use the **Add me as warehouse employee** action to quickly add yourself to the list of warehouse employees. For example, this is useful when you're testing the capabilities.

## See related [Microsoft training](/training/modules/get-started-warehouse-management/)

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Define an invoice posting policy for users](admin-setup-invoice-posting-policy.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
