---
    title: How to Create Bins | Microsoft Docs
    description: The most effective way to create the bins of your warehouse is to generate groups of similar bins in the bin creation worksheet, but you can also create your bins individually.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/07/2017
    ms.author: sgroespe

---
# Create Bins
The most effective way to create the bins of your warehouse is to generate groups of similar bins in the bin creation worksheet, but you can also create your bins individually from the location card. You can also use a function in the **Bin Creation Worksheet** window to create bins automatically.  

## To create a bin from the location card  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and choose the related link.  
2.  Select the location that you want to create a bin from, and then choose the **Bins** action.  
3. Choose the **New** action.
4. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To create bins individually in the bin creation worksheet  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bin Creation Worksheet**, and choose the related link.  
2.  Fill in on each line the fields that are necessary to name and characterize the bins you are creating.  
3.  Choose the **Create Bins** action.  

## To make bins automatically in the bin creation worksheet  
Before you start creating bins automatically, you should determine the kind of bins that are essential for your operations, as well as the most practical flow of items through the physical structure of your warehouse.  

> [!NOTE]  
>  As soon as you use a bin, you cannot delete it unless it is empty. But if you want to use another bin-naming system, you can use the reclassification journal to in effect move your items to a new bin system. This process is manual and takes time, however, so it is best to set up your bins correctly from the start.  

To work with the **Bin Creation Worksheet** window, you must be set up as a warehouse employee at the location where the bins exist. For more information, see [Set Up Warehouse Employees](warehouse-how-to-set-up-warehouse-employees.md).    

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bin Creation Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Bins** action.
3. In the **Calculate Bins** window, in the **Bin Template Code** field, select the bin template that you want to use as the model for the bins you are creating.
4.  Fill in a description for the bins you are in the process of creating.  
5.  To create the bin codes, fill in the **From No.** and **To No.** fields in the three categories shown in the window: **Rack**, **Section,**, and **Level.** The bin code can contain up to 20 characters.  

    > [!NOTE]  
    >  The number of characters that you have entered in the three categories for either field, for example, the characters you have entered in the three **From No.** fields, plus the field separators, if any, must be 20 or less.  

     You can use letters in the code as an identifying combination, but the letter you use must be the same in the **From No.** and **To No.** fields. For example, you might define the Rack part of the code as **From No. A01** and **To No. A10**. The program is not set up to generate codes with letter sequences, for example, from A01 to F05.  

6.  If you want a character, such as a hyphen, to separate the category fields you have defined as part of the bin code, fill in the **Field Separator** field with this character.  
7.  If you want the program not to create a line for a bin if it exists already, select the **Check on Existing Bin** field.  
8. When you have finished filling in the fields, choose the **OK** Button.

    The program creates a line for each bin in the worksheet. You can now delete some of the bins, for example, if you have a rack with a passageway through the first two levels of a couple of sections.  

9. When you have deleted all unnecessary bins, choose the **Create Bins** action, and the program will create bins for each line in the worksheet.  

Repeat the process for another set of bins until you have created all the bins in your warehouse.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
