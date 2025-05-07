---
title: Create production BOMs
description: Learn how to create a production bill of material (BOM), new versions of a production BOM, and how to use the quantity calculation formula.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: production bom, bills of material, 
ms.search.form: 911, 912, 917, 9287, 99000786, 99000787, 99000788, 99000789, 99000795, 99000797, 99000800, 99000809, 99000811, 99000812, 99000818
ms.date: 03/21/2025
ms.service: dynamics-365-business-central
---
# Create production BOMs

A production bill of material (BOM) holds master data that describes the components and subassemblies used in the production of an item. When you create a production order for an item, its production BOM governs the calculation of material requirements as represented on the **Prod. Order Components** page.

[!INCLUDE[prod_short](includes/prod_short.md)] also supports assembly BOMs. Use assembly orders to make end items from components in a process that one or more basic resources, which aren't machine or work centers, can do. Or, a process that can complete without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item. To learn more, go to [Assembly BOMs or Production BOMs](inventory-how-work-boms.md#assembly-boms-or-production-boms).  

> [!TIP]
> The **Contoso Coffee Demo Data** app includes demonstration products for a variety of production BOM scenarios that can be used on a test environment, including during a trial. Learn how to set up the Contoso Coffee Data and find walkthroughs for different scenarios at [Introduction to Contoso Coffee Demo Data](contoso-coffee/contoso-coffee-intro.md).

Before you can set up a routing, the following setups must be in place:  

- Item cards are created for parent items that take part in manufacturing. To learn more, go to [Register New Items](inventory-how-register-new-items.md).
- Production resources are set up. To learn more, go to [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## To create a production BOM

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOMs**, then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To edit the BOM, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  

    Proceed to fill in the production BOM lines.
5. In the **Type** field, select whether the item on this BOM line is an ordinary item or a production BOM. If the item on the line is a production BOM, then it must already exist as a certified production BOM.  
6. In the **No.** field, look up and select the item or production BOM in question, or type it in the field.  

   > [!TIP]
   > If you need to add several items, you can use the **Select items** action to select and add them. You can also use the **Edit in Excel** action. You can make changes to records in Excel, and then update the data in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more about the Edit in Excel action, go to [Edit in Excel](across-work-with-excel.md#edit-in-excel).

7. In the **Quantity per** field, enter how many units of the item go into the parent item, for example, 4 wheels for 1 car.  
8. In the **Scrap %** field, you can enter a fixed percentage of components that are scrapped during production. When the components are ready to be consumed in a released production order, this percentage is added to the expected quantity in the **Consumption Quantity** field in a production journal. To learn more, go to [Register Consumption and Output](production-how-to-register-consumption-and-output.md).  

    > [!NOTE]  
    > This scrap percentage represents components that are scrapped during production when picking from inventory. The scrap percentage on routing lines represents scrapped output before it's put in inventory.  

9. In the **Routing Link Code** field, enter a code to connect the component to a specific operation. To learn more, go to [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10. To copy lines from an existing production BOM, choose the **Copy BOM** action to select existing lines.  
11. Certify the production BOM.  
12. You can now attach the new production BOM to the card of the parent item in question. To learn more, go to [Register New Items](inventory-how-register-new-items.md).  

> [!NOTE]  
> [!INCLUDE [bom-standard-cost](includes/bom-standard-cost.md)] To recalculate the item's standard cost from the item card, choose the **Production** action, then choose the **Calc. Production Std. Cost** action. You can also calculate and update the standard cost for one or many items on the **Standard Cost Worksheet** page. To learn more, go to [Update Standard Costs](finance-about-calculating-standard-cost.md#updating-standard-costs-with-standard-cost-worksheet).  

## To create a new version of a production BOM

For example, use new versions of production BOMs when an item is replaced, or when a customer requires a special version of a product. The version principle enables various versions of a production BOM to be managed. The structure of the production BOM version corresponds to the structure of the production BOM. The basic difference is in the time validity of the versions. The starting date defines the validity.  

The starting date indicates the start of the period in which this version is valid. For all other considerations, the starting date is a filter criterion for calculations and evaluations. The BOM version is valid until the next version becomes valid for its starting date. You can quickly go to the certified BOM or BOM version that's valid on the work date by choosing the **Prod. Active BOM Version** action.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOMs**, then choose the related link.  
2. Select the production BOM to be copied, then choose the **Versions** action.  
3. Choose the **New** action.  
4. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
5. In the **Version Code** field, enter the unique identification of the version. Any combination of numbers and letters is permitted.  

    The newly created version is automatically assigned the status **New**.
6. When the BOM version is completed, setting the **Status** field to **Certified**.  

The time validity of the version is specified by the **Starting Date** field.  

> [!NOTE]  
> Select the **Item** option in the **Type** field to use an item from your item master data in the production BOM. If the item also has a production BOM, whereby the **Production BOM No.** field is filled in on the item card, this production BOM is also considered.  
>
> Select the **Production BOM** option if you want to use a phantom production BOM on the line.  
>
> Phantom production BOMs serve for structuring products. This production BOM type never leads to a finished product but is used exclusively for determining the dependent demand. Phantom production BOMs don't have their own item master data.

## Compare production BOM versions

Use the **Production BOM Version Comparison** page to access a list of all production BOM versions and items and the quantity used per item. You can use the matrix to compare different production BOM versions for the used items per version, including the original BOM as the first column. This page gives you an overview of all BOM versions and their respective quantities.

## Quantity calculation formula on production BOMs

The quantity is calculated taking into consideration different dimensions that are also entered on the production BOM lines. The dimensions refer to an order unit of the respective item. The length, width, depth, and weight can be entered as dimensions.  

The Calculation Formula, Length, Width, Depth, and Weight columns aren't displayed, because they're only used by some users. If you wish to use the calculation of the quantity, you must first display these columns.  

The calculation formula defines the relation of the individual components. The following options are available as a calculation formula:  

- **Empty** - No consideration of dimensions. (Quantity = Quantity per.)  
- **Length** - Quantity = Quantity per * Length  
- **Length x Width** - Quantity = Quantity per * Length x Width  
- **Length x Width x Depth** - Quantity = Quantity per x Length x Width x Depth  
- **Weight** - Quantity = Quantity per x Weight  
- **Fixed Quantity** - Quantity = Quantity per

> [!NOTE]
> The **Fixed Quantity** calculation formula ensures that the consumption of a component is the same, regardless of the scrap or output quantities. For production order components, when the **Calculation Formula** field is set to **Fixed Quantity**, the **Expected Quantity** field value is always equal to the **Quantity per** field. The scrap percentage that is defined on the same line is ignored. Fixed quantity is respected by the **Availability by BOM** report. The report will show the item as the bottleneck if the available quantity is less than the quantity in the **Quantity Per Parent** field. The **Able to Make Parent** and **Able to Make Top Item** fields are always blank, regardless of the available quantity. Fixed quantity is also included in calculations for standard costs. The lot size for the produced item impacts the cost that is allocated for one item.

### Example

A production BOM requires 70 metal parts with the dimensions length = 0.20 m and width = 0.15 m. Enter the values as follows: Calculation Formula = Length x Width, Length = 20, Width = 15, Quantity per = 70.

Quantity per x Length * Width, that is, Quantity = 70 x 0.20 m x 0.15 m = 2.1 m2, gives the quantity.  

## Related information

[Create Routings](production-how-to-create-routings.md)  
[Manage Product Variants](inventory-item-variants.md)  
[Walkthrough: Variants](contoso-coffee/manufacturing/variants.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
