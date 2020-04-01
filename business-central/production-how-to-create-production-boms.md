---
    title: How to Create Production BOMs | Microsoft Docs
    description: A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented on the **Prod. Order Components** page.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Production BOMs
A production bill of material (BOM) holds master data that describes the components and subassemblies used in the production of a parent item. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented on the **Prod. Order Components** page.

[!INCLUDE[d365fin](includes/d365fin_md.md)]  also support assembly BOMs. You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which are not machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item. For more information, see [Assembly BOMs or Production BOMs](inventory-how-work-boms.md#assembly-boms-or-production-boms).  

Before you can set up a routing, the following must be in place:  

- Item cards are created for parent items that take part in manufacturing. For more information, see [Register New Items](inventory-how-register-new-items.md).
- Production resources are set up. For more information, see [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## To create a production BOM  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To edit the BOM, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  

    Proceed to fill in the production BOM lines.
5. In the **Type** field, select whether the item on this BOM line is an ordinary item or a production BOM. If the item on the line is a production BOM, then it must already exist as a certified production BOM.  
6.  In the **No.** field, look up and select the item or production BOM in question, or type it in the field.  
7.  In the **Quantity Per** field, enter how many units of the item go into the parent item, for example, 4 wheels for 1 car.  
8.  In the **Scrap %** field you can enter a fixed percentage of components that are scrapped during production. When the components are ready to be consumed in a released production order, this percentage will be added to the expected quantity in the **Consumption Quantity** field in a production journal. For more information, see [Register Consumption and Output](production-how-to-register-consumption-and-output.md).  

    > [!NOTE]  
    >  This scrap percentage represents components that are scrapped during production when picking from inventory, whereas the scrap percentage on routing lines represents scrapped output before putting on inventory.  

9.  In the **Routing Link Code** field, enter a code to connect the component to a specific operation. For more information, see [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10. To copy lines from an existing production BOM, choose the **Copy BOM** action to select existing lines.  
11.  Certify the production BOM.  
12.  You can now attach the new production BOM to the card of the parent item in question. For more information, see [Register New Items](inventory-how-register-new-items.md).  

> [!NOTE]  
>  To recalculate the item’s standard cost from the item card, choose the **Manufacturing** action, and then choose the **Calc. Standard Cost** action.  

## To create a new versions of a production BOM
New versions of production BOMs are used when, for example, an item is replaced by another item, or when a customer requires a special version of a product. The version principle enables various versions of a production BOM to be managed. The structure of the production BOM version corresponds to the structure of the production BOM. The basic difference is in the time validity of the versions. The validity is defined by the starting date.  

The starting date indicates the start of the period in which this version is valid. For all other considerations, the starting date is a filter criterion for calculations and evaluations. The BOM version is valid until the next version becomes valid for its starting date.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.  
2.  Select the production BOM to be copied, and then choose the **Versions** action.  
3.  Choose the **New** action.  
4. Fill in the fields as necessary.
5. In the **Version Code** field, enter the unique identification of the version. Any combination of numbers and letters is permitted.  

    The newly created version is automatically assigned the status **New**.
6. When the BOM version is completed, setting the **Status** field to **Certified**.  

The time validity of the version is specified by the **Starting Date** field.  

> [!NOTE]  
>  Select the **Item** option in the **Type** field to use an item from your item master data in the production BOM. If the item also has a production BOM, whereby the **Production BOM No.** field is filled in on the item card, this production BOM is also considered.  
>   
>  Select the **Production BOM** option if you want to use a phantom production BOM on the line.  
>   
>  Phantom production BOMs serve for structuring products. This production BOM type never leads to a finished product, but is used exclusively for determining the dependent demand. Phantom production BOMs do not have their own item master data.

## Quantity Calculation Formula on Production BOMs  
The quantity is calculated taking into consideration different dimensions which are also entered on the production BOM lines. The dimensions refer to an order unit of the respective item. The length, width, depth and weight can be entered as dimensions.  

The Calculation Formula, Length, Width, Depth and Weight columns are not displayed, because they are only used by some users. If you wish to use the calculation of the quantity, you must first display these columns.  

The relation of the individual components is defined by the calculation formula. The following possibilities are available as a calculation formula:  

-  **Empty** - No consideration of dimensions. (Quantity = Quantity per.)  
-  **Length** - Quantity = Quantity per * Length  
-  **Length x Width** - Quantity = Quantity per * Length x Width  
-  **Length x Width x Depth** - Quantity = Quantity per x Length x Width x Depth  
-  **Weight** - Quantity = Quantity per x Weight  

### Example  
In a production BOM, seventy metal parts with the dimensions length = 0.20 m and width = 0.15 m are required. The values are entered as follows: Calculation Formula = Length x Width, Length = 20, Width = 15, Quantity per = 70. The quantity is given by the Quantity per x Length * Width, that is, Quantity = 70 x 0.20 m x 0.15 m = 2.1 m2.  

## See Also  
[Create Routings](production-how-to-create-routings.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
