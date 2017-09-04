---
    title: How to Create Production BOMs | Microsoft Docs
    description: A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented in the **Prod. Order Components** window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Create Production BOMs
A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented in the **Prod. Order Components** window.  

 **Prerequisites**  

-   Item cards are created for parent items and their components. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  

-   Gather all data about item structures: Top-level items, subassemblies, components, and their interrelation.  

### To fill in the production BOM header  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Production BOM**, and then choose the related link.  

2.  Create a new production BOM.  

3.  In the **No.** field, number the production BOM, for example, the same as the parent item.  

4.  In the **Description** field, name the production BOM, for example, the same as the parent item.  

5.  In the **Unit of Measure Code** field, select the parent item’s unit of measure code.  

6.  To edit the BOM, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  

### To fill in the production BOM lines  

1.  In the **Type** field, select whether the item on this BOM line is an ordinary item or a production BOM. If the item on the line is a production BOM, then it must already exist as a certified production BOM.  

2.  In the **No.** field, look up and select the item or production BOM in question, or type it in the field.  

3.  In the **Quantity Per** field, enter how many units of the item go into the parent item, for example, 4 wheels for 1 car.  

4.  In the **Scrap %** field you can enter a fixed percentage of components that are scrapped during production. When the components are ready to be consumed in a released production order, this percentage will be added to the expected quantity in the **Consumption Quantity** field in a production journal. For more information, see [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md).  

    > [!NOTE]  
    >  This scrap percentage represents components that are scrapped during production when picking from inventory, whereas the scrap percentage on routing lines represents scrapped output before putting on inventory.  

5.  In the **Routing Link Code** field, enter a code to connect the component to a specific operation. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  

     Routing links between operations and components ensure that material consumption is not posted until it has actually been consumed. In addition, routing links provide a process view in the **Production Journal** window where components are listed under the linked operation. For more information, see [How to: Create Routing Links](../how-to-create-routing-links.md).  

6.  To copy lines from an existing production BOM, on the **Actions** tab, in the **Functions** group, choose **Copy BOM** to select existing lines.  

7.  Certify the production BOM.  

8.  You can now attach the new production BOM to the card of the parent item in question. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  

> [!NOTE]  
>  To recalculate the item’s standard cost from the item card, on the **Navigate** tab, in the **Bill of Material** group, choose **Manufacturing**, and then choose **Calc. Standard Cost**.  

# How to: Create New Versions of Production BOMs
New versions of production BOMs are used when, for example, an item is replaced by another item, or when a customer requires a special version of a product.  

### To create a new version of a production BOM  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Production BOM**, and then choose the related link.  

2.  Select the production BOM to be copied.  

3.  On the **Navigate** tab, in the **Prod. BOM** group, choose **Versions**.  

4.  On the **Home** tab, in the **New** group, choose **New**.  

5.  Fill in the fields of the new production BOM version for the BOM you selected. Enter a value in the **Version Code** field.  

     The newly created version is automatically assigned the status **New**.  

     The time validity of the version is specified by the **Starting Date** field.  

> [!NOTE]  
>  Select the **Item** option in the **Type** field to use an item from your item master data in the production BOM. If the item also has a production BOM, whereby the **Production BOM No.** field is filled in on the item card, this production BOM is also considered.  
>   
>  Select the **Production BOM** option if you want to use a phantom production BOM on the line.  
>   
>  Phantom production BOMs serve for structuring products. This production BOM type never leads to a finished product, but is used exclusively for determining the dependent demand. Phantom production BOMs do not have their own item master data.

# Production BOM Versions
The production BOMs support the version principle which is explained below.  

 The version principle enables various versions of a production BOM to be managed. The structure of the production BOM version corresponds to the structure of the production BOM. The basic difference is in the time validity of the versions. The validity is defined by the starting date.  

 The starting date and the status are decisive for using the production BOM version in production.  

## Starting Date  
 The starting date indicates the start of the period in which this version is valid. For all other considerations, the starting date is a filter criterion for calculations and evaluations. The BOM version is valid until the next version becomes valid for its starting date.  

## Status  
 The status of the version can correspond to the following options:  

-   **New**  

     The **New** status is automatically filled in when a new version is created. In this status, all changes can be made, and no consideration is made in the calculations.  

-   **Certified**  

     The status is set to **Certified** when the version of the production BOM has been created completely and correctly. To do this, it must be checked first by appropriately qualified employees. After setting the status to **Certified**, the BOM is considered in calculations (according to starting date and ending date). No changes to the version are possible.  

-   **Under Development**  

     If changes to the production BOM version are necessary, the status is set to **Under Development** to allow changes.  

-   **Closed**  

     Indicates that the BOM version is no longer valid.  

## Calculation Formula  
 The quantity is calculated taking into consideration different dimensions which are also entered on the lines. The dimensions refer to an order unit of the respective item. The length, width, depth and weight can be entered as dimensions.  

 The Calculation Formula, Length, Width, Depth and Weight columns are not displayed, because they are only used by some users. If you wish to use the calculation of the quantity, you must first display these columns.  

 The relation of the individual components is defined by the calculation formula. The following possibilities are available as a calculation formula:  

-   Empty  

     No consideration of dimensions. (Quantity = Quantity per.)  

-   Length  

     Quantity = Quantity per * Length  

-   Length * Width  

     Quantity = Quantity per * Length * Width  

-   Length * Width * Depth  

     Quantity = Quantity per * Length * Width * Depth  

-   Weight  

     Quantity = Quantity per * Weight  

### Example  
 In a production BOM, seventy metal parts with the dimensions length = 0.20 m and width = 0.15 m are required. The values are entered as follows: Calculation Formula = Length * Width, Length = 20, Width = 15, Quantity per = 70. The quantity is given by the Quantity per * Length * Width, that is, Quantity = 70 * 0.20 m * 0.15 m = 2.1 m2.  

## See Also  
 [Define Material and Process Structure](../define-material-and-process-structure.md)   
 [Assembly BOMs or Production BOMs](../assembly-boms-or-production-boms.md)
