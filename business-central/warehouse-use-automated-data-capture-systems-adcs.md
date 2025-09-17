---
title: Use Automated Data Capture Systems (ADCS) foundation
description: Learn how to use your automatic data capture system (ADCS) to register the movement of items in the warehouse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.form: 7700, 7703, 7704, 7706, 7707, 7710, 9813, 9814
---
# Use Automated Data Capture Systems (ADCS) foundation

> [!Important]
> The Automated Data Capture System (ADCS) solution provides a way for [!INCLUDE[prod_short](includes/prod_short.md)] to communicate with handheld devices through web services. You must work with a Microsoft partner who can provide the link between the web service and the specific handheld device. 

You can use your automatic data capture system (ADCS) to register the movement of items in the warehouse and to register some journal activities, such as quantity adjustments in the warehouse item journal and physical inventories. ADCS typically involves scanning a barcode.

To use ADCS, you must give each item stored in the warehouse an item identifier. You must also set up miniforms, handheld functions, data exchanges, and specify settings for fields that control ADCS. You specify whether to use ADCS on the location card of a warehouse.

Based on the needs of your warehouse, you define the amount of information displayed in the miniform setup for the particular handheld device. The following are examples of information that you can display:  

- Data from tables within [!INCLUDE[prod_short](includes/prod_short.md)], such as a list of pick documents from which the user can select.  
- Text information.  
- Messages to show confirmations or errors about activities performed and registered by the handheld device user.

## To enable Web Services for ADCS

To use Automated Data Capture System, you must enable the ADCS web service. You must work with a Microsoft partner who can implement a web service that can connect ADCS and a specific handheld device. You can learn more about the web service for ADCS by examining codeunit 7714. 
 
## To set up a warehouse to use ADCS  

To use ADCS, you must specify which warehouse locations use the technology.  

> [!NOTE]  
> We recommend that you don't set up a warehouse to use ADCS if it also has a bin capacity policy.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Locations**, and choose the related link.
2. Select the warehouse for which you want to enable ADCS, and then choose the **Edit** action.
3. On the **Location Card** page, turn on the **Use ADCS** toggle.  

## To specify an item to use ADCS  

Each warehouse item that you want to use with ADCS must be assigned an identifier code to link it with its item number. For example, you can use the item's bar code as the identifier code. An item can also have multiple identifier codes. You may find this useful in the case where an item is available in various units of measures, such as pieces and pallets. In this case, assign an identifier code to each.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.  
2. Select an item from the list that is part of your ADCS solution, and then choose the **Edit** action.
3. On the **Item Card** page, choose the **Identifiers** action.
4. On the **Item Identifiers** page, choose the **New** action.
5. In the **Code** field, specify the identifier for the item. For example, the identifier could be the item's bar code number.  

    You can also enter a **Variant Code** and a **Unit of Measure** code.  

6. If needed, enter multiple codes for each item.
7. Choose the **OK** button.  
8. To review the information, choose the **Identifier Code** field to open the **Item Identifiers** page.

## To add an ADCS user  

You can add any user to an ADCS. When you do, the user must provide a password. Optionally, you can also provide a connection that identifies the ADCS user as a warehouse employee. The ADCS user password can be different from their sign-in password. Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **ADCS Users**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Name** field, enter a name for the user. The name can't have more than 20 characters, including spaces.  
4. In the **Password** field, enter a password.  

### To specify that a warehouse employee is an ADCS user  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Warehouse Employees**, and then choose the related link.  
2. If needed, add a new warehouse employee. Learn more at [Set Up Warehouse Employees](warehouse-how-to-set-up-warehouse-employees.md).  
3. Choose the **Edit List** action.  
4. Select a warehouse employee from the list. In the **ADCS User** field, choose the name of an ADCS user from the list.  

> [!NOTE]  
> The default warehouse for the employee must be one that uses ADCS.

## To create and customize miniforms

You use miniforms to describe the information that you want to present on a handheld device. For example, you can create miniforms to support the warehouse activity of picking items. After you create a miniform, you can add functions to it for the common actions that a user takes with handheld devices, such as moving up or down a line.  

> [!NOTE]
> To implement or change the functionality of a miniform function, you must create a new codeunit for the **Handling Codeunit** field to perform the required action or response. You can learn more about ADCS functionality by examining the following codeunits:
>
> * 7705
> * 7706
> * 7712
> * 7713  

### To create a miniform for ADCS  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Miniforms**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Code** field, enter a code for the miniform. Optionally, enter values in all other fields.  

    Turn on the **Start Miniform** toggle to indicate that the miniform is the first form that's available when a user signs in.  

4. On the **Lines** FastTab, define the fields that appear on the miniform. The order in which you enter lines is the order in which the lines appear on the handheld device.  

When you have created a miniform, the next steps are to create functions and to associate functionality for various keyboard inputs.  

### To customize miniform functions

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Miniforms**, and then choose the related link.  
2. Select a miniform from the list, and then choose the **Edit** action.  
3. Choose the **Functions** action.  
4. In the **Function Code** drop-down list, select a code to represent the function that you want to associate with the miniform. For example, you can select **ESC** to associate functionality with the **ESC** key.  

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
