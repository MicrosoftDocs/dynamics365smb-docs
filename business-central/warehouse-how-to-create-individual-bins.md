---
title: Create bins
description: Generate groups of similar bins in the bin creation worksheet, create bins individually on the location card, or automatically on the Bin Creation Worksheet. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 7368, 7369, 7370, 7371, 7372, 7373
ms.date: 12/13/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create bins

The most effective way to create the bins of your warehouse is to generate groups of similar bins in the bin creation worksheet, but you can also create your bins individually from the location card. You can also use a function on the **Bin Creation Worksheet** page to create bins automatically.  

## To create a bin from the location card

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Locations**, and choose the related link.  
2.  Select the location that you want to create a bin from, and then choose the **Bins** action.  
3. Choose the **New** action.
4. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### The dedicated field

The **Dedicated** field on the **Bins** page specifies that quantities in the bin are protected from being picked for other demands. However, quantities in dedicated bins can still be reserved. Accordingly, the quantities in dedicated bins are included in the **Total Available Quantity** field on the **Reservation** page.

Making a bin dedicated results in similar functionality in basic warehousing to using bin types, which is only available in advanced warehousing. For more information, see [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).

### Example

A work center is set up with a bin code in the **To-Production Bin Code** field. Production order component lines with that bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands might pick or consume from that bin because they're still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code.

> [!Caution]
> Items in dedicated bins are not protected when they are picked and consumed as production or assembly components with the **Inventory Pick** page. For more information, see [Pick for Production or Assembly in Basic Warehouse Configurations](warehouse-how-to-pick-for-production.md).

## To create bins individually in the bin creation worksheet

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Bin Creation Worksheet**, and choose the related link.  
2.  Fill in on each line the fields that are necessary to name and characterize the bins you're creating.  
3.  Choose the **Create Bins** action.  

## To make bins automatically in the bin creation worksheet

Before you start creating bins automatically, you should determine the kind of bins that are essential for your operations, and the most practical flow of items through the physical structure of your warehouse.  

> [!NOTE]  
> As soon as you use a bin, you cannot delete it unless it is empty. But if you want to use another bin-naming system, you can use the reclassification journal to in effect move your items to a new bin system. This process is manual and takes time, however, so it is best to set up your bins correctly from the start.  

To work with the **Bin Creation Worksheet** page, you must be set up as a warehouse employee at the location where the bins exist. For more information, see [Set Up Warehouse Employees](warehouse-how-to-set-up-warehouse-employees.md).    

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Bin Creation Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Bins** action.
3. On the **Calculate Bins** page, in the **Bin Template Code** field, select the bin template that you want to use as the model for the bins you're creating.
4.  Fill in a description for the bins you are in the process of creating.  
5.  To create the bin codes, fill in the **From No.** and **To No.** fields in the three categories shown on the page: **Rack**, **Section,**, and **Level.** The bin code can contain up to 20 characters.  

    > [!NOTE]  
    >  The number of characters that you have entered in the three categories for either field, for example, the characters you have entered in the three **From No.** fields, plus the field separators, if any, must be 20 or less.  

     You can use letters in the code as an identifying combination, but the letter you use must be the same in the **From No.** and **To No.** fields. For example, you might define the Rack part of the code as **From No. A01** and **To No. A10**. The application isn't set up to generate codes with letter sequences, for example, from A01 to F05.  

6.  If you want a character, such as a hyphen, to separate the category fields you have defined as part of the bin code, fill in the **Field Separator** field with this character.  
7.  If you want application not to create a line for a bin if it exists already, select the **Check on Existing Bin** field.  
8. When you finish filling in the fields, choose the **OK** button.

    The application creates a line for each bin in the worksheet. You can now delete some of the bins, for example, if you have a rack with a passageway through the first two levels of a couple of sections.  

9. When you delete all unnecessary bins, choose the **Create Bins** action, and application creates bins for each line in the worksheet.  

Repeat the process for another set of bins until you create all the bins in your warehouse.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)    
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
