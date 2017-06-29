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
# How to: Create Bin Content in Worksheets
When you have created your bins, you can create the bin content that you want for each bin in the bin content creation worksheet.  
  
### To create bin content in the worksheet  
  
1.  In the **Search** box, enter **Bin Content Creation Worksheet**, and then choose the related link.  
  
2.  On the worksheet header, in the **Name** field, select the worksheet of the location where you want to create bin contents.  
  
3.  In the **Bin Code** field, select the code of the bin for which you want to define bin content.   
    If you are using directed put\-away and pick in this location, the fields relating to that particular bin, such as **Bin Type**, **Warehouse Class Code**, and **Bin Ranking**, will be filled in automatically. This is information that you need to consider as you define the bin content.  
  
4.  Select the item that you want to assign to the bin, and fill in the fields related to the bin content. If you are using directed put\-away and pick, and want to use the **Calculate Bin Replenishment** function, fill in the **Max. Qty.** and **Min. Qty.** fields.  
  
     To set this bin as the preferred bin for the item even if the bin quantity is **0** and all other put\-away criteria equal, select the **Fixed** field.  
  
5.  Repeat steps 3 through 4 for each item you want to assign to a bin.  
  
6.  On the **Home**  tab, in the **Process** group, choose **Print** to preview and print the bin content you have entered in the worksheet. Continue to revise the bin content until you are satisfied.  
  
7.  When you have finished, on the **Actions** tab, in the **Functions** group, choose **Create Bin Content**.  
  
 In this worksheet, you can work with a number of bin content lines for a number of bins and thereby obtain a good overview of what you are putting into various bins in a given zone, aisle, or rack.  
  
## See Also  
 [How to: Assign Default Bins to Items](../WarehouseActivities/how-to-assign-default-bins-to-items.md)   
 [How to: Modify Bin Content](../WarehouseActivities/how-to-modify-bin-content.md)