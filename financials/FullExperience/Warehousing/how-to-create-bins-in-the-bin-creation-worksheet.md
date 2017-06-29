---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Create Bins in the Bin Creation Worksheet
In the bin creation worksheet, you can create bins manually or you can allow the program to create a number of similar bins in one operation.  
  
 Before you start creating bins in the worksheet, you should determine the kind of bins that are essential for your operations, as well as the most practical flow of items through the physical structure of your warehouse.  
  
> [!NOTE]  
>  As soon as you use a bin, you cannot delete it, since entries associated with it have been created. But if you want to use another bin-naming system, you can use the reclassification journal to in effect move your items to a new bin system. This process is manual and takes time, however, so it is best to set up your bins correctly from the start.  
  
> [!NOTE]  
>  To work with the **Bin Creation Worksheet** window, you must be set up as a warehouse employee at the location where the bins exist. For more information, see [How to: Set Up Warehouse Employees](../WarehouseActivities/how-to-set-up-warehouse-employees.md).  
  
### To make bins in the bin creation worksheet  
  
1.  In the **Search** box, enter **Bin Templates**, and then choose the related link.  
  
2.  In the **Search** box, enter **Bin Creation Worksheet**, and then choose the related link.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Calculate Bins**. The **Calculate Bins** batch job request window opens.  
  
4.  In the **Bin Template Code** field, select the bin template that you want to use as the model for the bins you are creating.  
  
5.  Fill in a description for the bins you are in the process of creating.  
  
6.  To create the bin codes, fill in the **From No.** and **To No.** fields in the three categories shown in the window: **Rack**, **Section,**, and **Level.** The bin code can contain up to 20 characters.  
  
    > [!NOTE]  
    >  The number of characters that you have entered in the three categories for either field, for example, the characters you have entered in the three **From No.** fields, plus the field separators, if any, must be 20 or less.  
  
     You can use letters in the code as an identifying combination, but the letter you use must be the same in the **From No.** and **To No.** fields. For example, you might define the Rack part of the code as **From No. A01** and **To No. A10**. The program is not set up to generate codes with letter sequences, for example, from A01 to F05.  
  
7.  If you want a character, such as a hyphen, to separate the category fields you have defined as part of the bin code, fill in the **Field Separator** field with this character.  
  
8.  If you want the program not to create a line for a bin if it exists already, select the **Check on Existing Bin** field.  
  
9. When you have finished filling in the fields, choose the **OK** Button. The program creates a line for each bin in the worksheet. You can now delete some of the bins, for example, if you have a rack with a passageway through the first two levels of a couple of sections.  
  
    > [!NOTE]  
    >  You can at any time print out a list of the bins you have calculated. On the **Home** tab, in the **Process** group, choose **Print.**  
  
10. When you have deleted all unnecessary bins, on the **Actions** tab, in the **Functions** group, choose **Create Bins**, and the program will create bins for each line in the worksheet.  
  
 Repeat the process for another set of bins until you have created all the bins in your warehouse.  
  
## See Also  
 [How to: Create Individual Bins](../WarehouseActivities/how-to-create-individual-bins.md)   
 [How to: Set Up Bin Contents](../WarehouseActivities/how-to-set-up-bin-contents.md)