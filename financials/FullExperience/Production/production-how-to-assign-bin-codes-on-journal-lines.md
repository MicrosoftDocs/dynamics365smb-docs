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
# How to: Assign Bin Codes on Journal Lines
When you create a consumption journal or an output journal, and the warehouse location is set up to use bins but not directed put-away and pick, you assign a bin code to the journal line to indicate that the item will either come from or be placed in that bin. In the following procedure, a consumption journal is used as an example.  
  
### To assign a bin code to a journal line  
  
1.  In the **Search** box, enter **Consumption Journal**, and then choose the related link.  
  
2.  Enter the relevant line information and fill in the **Location Code** and **Bin Code** fields.  
  
     If the **Location Code** and **Bin Code** fields are not visible on the journal line, you can add them. Open the shortcut menu for the column headings, and choose **Choose Columns** to add them to the list of displayed columns.  
  
    > [!NOTE]  
    >  If the item has a default bin assigned, the **Bin Code** field is automatically filled in with the item's default bin for that location when you enter the location code on the line.  
  
    > [!TIP]  
    >  To facilitate the putting away or picking of items, you can print out the document lines with the bin code information. On the **Actions** tab, in the **General** group, choose **Print**.  
  
3.  Complete the journal and post it.  
  
 During the posting, warehouse entries are created to record the item quantity in the bin.  
  
## See Also  
 Bins   
 [How to: Set Up Locations to Use Bins](../how-to-set-up-locations-to-use-bins.md)