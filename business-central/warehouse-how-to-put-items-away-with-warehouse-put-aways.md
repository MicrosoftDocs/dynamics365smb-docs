---
title: How to put items away with warehouse put-aways
description: Learn about the different ways to use warehouse put-aways to put away received items.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 04/23/2024
ms.custom: bap-template
ms.search.forms: 7352, 7333

---
# Put items away with warehouse put-aways

In [!INCLUDE[prod_short](includes/prod_short.md)], you receive items and put them away using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

Learn more at [Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

This article refers to method D in the table, and assumes that receiving has already happened. Learn more at [Receive Items](warehouse-how-receive-items.md).

When a location is set up to require warehouse put-away processing and warehouse receive processing, use warehouse put-away documents to control how items are put away. When you post a warehouse receipt, source documents such as purchase, inbound transfer, or sales return orders, are updated. The quantity received is posted to the item ledger, and the lines for the received items are sent to the put-away function in the warehouse.

Depending on the value in the **Use Put-away Worksheet** field on the **Location card**, the lines are either made available to the put-away worksheet or used to generate put-away documents immediately. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

In addition to the standard ways to create warehouse put-aways that this article describes, you can create put-aways from the related posted warehouse receipt. This is useful if you have deleted put-away lines, or if you decide not to use the put-away worksheet, because you can create or recreate put-away instructions from the posted receipt lines.

## Zone and bin codes

At locations that are set up to use directed put-away and pick, the following settings are required to determine the best place to put the items:  

* A put-away template is set up. Learn more at [Set Up Put-away Templates](warehouse-how-to-set-up-put-away-templates.md).  
* The weight, cubage, and special storage requirements of the item or stock-keeping unit are defined.
* The capacity, bin type, and bin ranking are defined for the bins.  

The bin ranking is used when more than one bin matches the criteria on the put-away template. If both the put-away template criteria and the bin ranking are the same for more than one bin, the bin with the highest number is selected.

## To create put-away documents in bulk with the put-away worksheet  

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

You can create put-away documents for multiple receipts at the same time on the **Put-away Worksheet** page.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Put-away Worksheets**, and then choose the related link.  
2. Choose the **Get Warehouse Documents** action. The **Put-away Selection** page opens.  

    The list contains all posted receipts that are ready to be put away, including those for which put-away instructions have already been created. Documents with put-away lines that have been completely put away and registered are not shown on this list.  
3. Select the documents that you want to work on. You can work on lines from several documents at the same time.  

    > [!NOTE]  
    > If you select a receipt or internal put-away document for which you've already created instructions for all lines, [!INCLUDE[prod_short](includes/prod_short.md)]] informs you that there's nothing to handle.  

4. Fill in the **Sorting Method** field to sort the lines.  

    > [!NOTE]  
    > The way the lines are sorted in the worksheet doesn't automatically carry through to the put-away instruction. However, the same opportunities for sorting and bin ranking exist. You can recreate the line order you plan in the worksheet when you create the put-away instructions or sort in the put-away instructions.

5. Fill in the **Qty. to Handle** field. Choose the **Autofill Qty.to Handle** action, or fill in the fields manually.  
6. If needed, edit the lines manually. You can delete lines, for example, if some items need to be put away in a bin that's far away from the bins for the other items.  

    > [!NOTE]  
    > When you delete lines they're only deleted from this worksheet. They aren't deleted from the put-away selection.  

7. Choose the **Create Put-away** action. The **Create Document** page opens, where you can add more information to the put-away you're creating.  

    * You can assign the put-away to a specific employee.  
    * You can sort the put-away instruction lines as you did in the worksheet or by bin ranking. When you sort according to bin ranking, the *Take* lines appear first, because most receipt bins have a 0 bin ranking. The *Place* lines appear last, starting with the bins with the lowest bin ranking. If you have structured your warehouse so bins of similar bin ranking are side by side, sorting lines in this way will save steps for warehouse employees.  
    * You can choose not to include the lines that [!INCLUDE [prod_short](includes/prod_short.md)] created when it converted a large unit of measure to smaller units of measure by selecting the **Set Breakbulk Filter** field. Learn more about breakbulk at [Enable Automatic Breaking Bulk with Directed Put-away and Pick](warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md).  
    * You can choose not to have the **Qty. to Handle** field automatically filled in on the put-away instructions.  
    * You can choose to print the document immediately.  

8. Choose **OK** to create the put-away.  

## To create a put-away from a posted receipt

If a location uses both put-away processing and receive processing and you have deleted put-away lines, or if you use directed put-away and pick and have decided not to use the put-away worksheet, you can create or recreate put-away instructions for the posted receipt lines.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Warehouse Receipts**, and then choose the related link.  
2. Select a posted receipt to put away.  
3. Choose the **Card** action.  

    If the **Document Status** field is blank, the receipt has not been put away at all. Otherwise, the field indicates whether the receipt is partially or completely put-away.  

4. If the receipt is partially put away or not put away at all, choose the **Create Put-away** action.  
5. Fill in the fields as necessary, and then choose **OK**.  

## To put items away

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Warehouse Put-aways**, and then choose the related link.

2. Open the warehouse put-away that's ready to handle.  
3. If your warehouse requires, enter your user ID when you start work on a put-away.  

    You can sort the put-away lines by various criteria, for example, by item, shelf number, or due date. Sorting can help optimize the put-away process, for example:

    * If the Take and Place lines for each receipt line don't immediately follow one another, and you want them to, sort the lines by selecting **Item** in the **Sorting Method** field.  
    * If bin rankings reflect the physical layout of the warehouse, use the **Bin Ranking** sorting method to organize the work by bin locations.

  > [!NOTE]  
  > Lines are sorted in ascending order by the selected criteria. If you sort by document, sorting is done first by document type based on the **Warehouse Activity Source Document** field. If you sort by ship-to, sorting is done first by destination type based on the **Warehouse Destination Type** field.

4. Perform the actions.

    If a bin code is mandatory for the locations, each receipt line becomes at least two lines in the warehouse put-away, as follows.  

    * The first line, with **Take** in the **Action Type** field, indicates where the items are located in the receiving area. You can't change the zone and bin on this line.  
    * The next line, with **Place** in the **Action Type** field, shows where you must place the items in the warehouse. If you receive a large number of items on one receipt line, you might have to put the items away in several bins, so there's a Place line for each bin. 

    > [!NOTE]
    > If you must place the items for one line in more than one bin, for example because the designated bin is full, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.

5. When you have placed all the items in bins as instructed, choose the **Register Put-away** action.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
