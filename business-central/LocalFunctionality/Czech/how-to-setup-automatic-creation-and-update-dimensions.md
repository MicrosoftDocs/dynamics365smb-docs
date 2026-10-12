---
title: Set up automatic creation and update of dimensions [CZ]
description: Learn how to automatically create and update dimensions and dimension values for master records in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Automatic creation and update of dimensions in the Czech version

Instead of setting up a dimension and its values manually for each master record, you can let [!INCLUDE[prod_short](../../includes/prod_short.md)] create the dimension value and assign it as a default dimension automatically whenever a new record is created. The feature supports master tables such as customers, vendors, items, G/L accounts, employees, bank accounts, fixed assets, resources, resource groups, jobs, work centers, item charges, insurance policies, responsibility centers, salespersons/purchasers, campaigns, cash flow manual expenses and revenues, and their related templates.

## Set up automatic dimension creation

1. Choose the **Tell Me** icon, enter **Dimensions**, and then choose the related link.
1. On the **Dimensions** page, select the dimension that you want to create and assign automatically, and then choose the **Auto-Create Default Dimension Setup** action.
1. On the **Auto. Create Default Dimensions** page, choose **New**.
1. In the **Table ID** field, select the master table that the automatic dimension creation applies to.
1. In the **Dim. Description Field ID** field, optionally select the field on the master table that provides the description for the dimension value, such as a name field.
1. In the **Dim. Description Update** field, select whether the dimension value's description is left blank, created once, or kept in sync every time the source field changes.
1. In the **Dim. Description Format** field, optionally enter a formatting string to apply to the description.
1. In the **Auto. Create Value Posting** field, select the value posting that's set on the default dimension that's created automatically.
1. Select the **Not Create Default Dimension** field if you want the dimension value to be created, but you don't want a default dimension assigned to the record.

When these steps are complete, [!INCLUDE[prod_short](../../includes/prod_short.md)] automatically creates the dimension value and default dimension the next time you create a record in the selected table.

## Update dimensions for existing records

If you set up automatic dimension creation after you already have records in a table, use the **Update automatic default dimensions** action on the **Auto. Create Default Dimensions** page to initialize the dimension values and default dimensions for the existing records. Select the setup lines that you want to apply, and then choose the action. Because this action can take a while and can't be undone, confirm that you want to continue when prompted.

## Related information

- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
