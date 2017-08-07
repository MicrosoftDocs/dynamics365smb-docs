---
    title: How to Put Items Away with Warehouse Put-aways | Microsoft Docs
    description: When your location is set up to require warehouse put-away processing and warehouse receive processing, you use the warehouse put-away documents function to control the putting away of items.
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
# How to: Put Items Away with Warehouse Put-aways
When your location is set up to require warehouse put-away processing and warehouse receive processing, you use the warehouse put-away documents function to control the putting away of items.  
  
 When you post a warehouse receipt, the source documents, such as purchase, inbound transfer, or sales return orders, are updated, the quantity received is posted to the item ledger, and the lines about the items received are sent to the put-away function in the warehouse. If you have internal put-away and pick, the internal put-away can also create lines for put-away.  
  
 Depending on the warehouse setup, the lines are either made available to the put-away worksheet or used to generate put-away instructions immediately. For more information, see [How to: Plan Put-aways in Worksheets](../how-to-plan-put-aways-in-worksheets.md).  
  
 In addition to the standard ways to create warehouse put-aways that are described in this topic, you can create the put-away from the related posted warehouse receipt. For more information, see [How to: Create Put-aways from Posted Receipts](../how-to-create-put-aways-from-posted-receipts.md).  
  
### To put items away without directed put-away and pick  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Put-aways**, and then choose the related link.  
  
2.  Open the warehouse put-away that is ready to handle.  
  
     You can sort the put-away lines by various criteria, for example, by item, shelf number, or due date, and thereby optimize the put-away process.  
  
3.  On each line, in the **Qty. to Handle** field, enter the quantity you want to put away.  
  
4.  To print a **Whse. Put-away Report**, choose the **Print** button.  
  
5.  After you have completed putting the items away, on the **Actions** tab, in the **Registering** group, choose **Register Put-away** to record the completion of the activity and make the items available for picking.  
  
### To put items away with directed put-away and pick  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Put-aways**, and then choose the related link. If put-away instructions have been created, a warehouse put-away is visible.  
  
2.  Open the warehouse put-away that you want to work on.  
  
3.  If your warehouse requires, enter your user ID on the **General** FastTab when you begin work on a particular put-away.  
  
4.  To print the instructions, choose the **Print** button.  
  
5.  Perform the take and place actions indicated in the **Action Type** field on the lines.  
  
     Note that each receipt line has become at least two lines in the warehouse put-away:  
  
    -   The first line, with **Take** in the **Action Type** field, indicates where the items are located in the receiving area. You cannot change the zone and bin field on this line.  
  
    -   The next line, with **Place** in the **Action Type** field, shows where you must place the items in warehouse storage. If the warehouse has received a large number of items on one receipt line, they may have to be put away in several bins, so there is a **Place** line for each bin.  
  
         If the Take and Place lines for each receipt line do not immediately follow one another, and you want them to do so, you can sort the lines by selecting **Item** in the **Sorting Method** field on the **General** FastTab.  
  
         If the physical layout of the warehouse reflects the bin rankings, you can use the **Bin Ranking** sorting method to prepare a put-away round that will minimize your steps through the warehouse.  
  
6.  When you have placed all the items in bins as instructed, on the **Actions** tab, in the **Registering** group, choose **Register Put-away**.  
  
 At locations that are set up to use directed put-away and pick, the following settings are prerequisites for the procedure above:  
  
-   A put-away template is set up. For more information, see [How to: Set Up Put-away Templates](../how-to-set-up-put-away-templates.md).  
  
-   The weight, cubage, and special storage requirements of the item or stockkeeping unit are defined. For more information, see Gross Weight.  
  
-   The capacity, bin type, and bin ranking of the bins. For more information, see Bin Ranking.  
  
 The bin ranking is taken into consideration when more than one bin matches put-away template criteria. If both the put-away template criteria and the bin ranking are the same for more than one bin, the bin with the highest number is selected.  
  
## See Also  
 Warehouse Receipt   
 Warehouse Put-away   
 [Put Items Away](../put-items-away.md)   
 [How to: Prepare Shipments](../How%20to:%20Prepare%20Shipments.md)   
 [How to: Cross-Dock Items](../how-to-cross-dock-items.md)   
 [How to: Receive Items](../how-to-receive-items.md)