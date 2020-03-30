---
    title: How to Restructure Warehouses | Microsoft Docs
    description: You may want to restructure your warehouse with new bin codes and new bin characteristics.
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
# Restructure Warehouses
You may want to restructure your warehouse with new bin codes and new bin characteristics. You will not undertake this kind of activity very often, but situations can occur where a reclassification is necessary to achieve or maintain a more efficient operation. For example:  

- You might want to switch to bin codes that support the use of automatic data capture, for example, with hand-held devices.  
- The warehouse may have purchased a new rack system that gives new possibilities in item storage.  
- The company may have altered its item assortment and moved the warehouse to a new physical location to accommodate this change.  

If your warehouse is set up to use bins but not directed put-away and pick, restructure your warehouse by creating the new bins that you want to use in the future.  

## To restructure a basic warehouse that uses bins only  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  On the **Warehouse** FastTab, set the **Default Bin Selection** field to **Last-Used Bin**.  
3.  Move all the contents of your current bins to the new bins that you have just created.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclassification Journal**, and then choose the related link.  
    2.  Select a journal line, and then choose the **Get Bin Content** action.  
    3.  On the **Bin Content** FastTab, set filters in the **Location Code**, **Bin Code**, and **Item No.** fields to specify the content that you want to move.  
    4.  Choose the **OK** button to fill a journal line.  
    5.  In the **New Bin Code** field, select the bin to which the items should be moved.  
    6.  Repeat steps b through e for all bin content that you want to move.  
    7.  Choose the **Post** action.  

You have now emptied the bins where the items used to be. The default bins for your items have now been changed to the new bins.  

## To restructure an advanced warehouse that uses directed put-away and pick  

1.  Create the new bins that you want to use in the future. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md).  
2.  Move all the contents of your current bins to the new bins that you just created.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Reclassification Journal**, and then choose the related link.  
    2.  For the bins where no real movement of items is involved, create a line for each of your current bins in the **Warehouse Reclassification Journal** with the old bin code, **From Bin Code**, and the new bin code, **To Bin Code**.  
    3.  If some of the movements involve actual physical movements that you want employees to perform, use **Movement Worksheets** to prepare movement instructions instead of using the warehouse reclassification journal. For more information, see [Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md).  

3.  When the old bins are emptied, reclassify them as **QC** type bins to ensure that they are not included in item flows.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
    2.  Select the line with the location, and then choose the **Bins** action.  
    3.  On the **Bins** page, in the **Bin Type Code** field, enter **QC** for each of the old bins that you emptied in step 3 in the previous procedure.  

You have now removed the bins from the warehouse flow, and reclassified them as QC bins. QC bins have none of the activity fields on the **Bin Types** page selected and are therefore not considered by the item flow. For more information, see [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).  

## To delete a bin  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  Select the location where you want to delete bins. Choose the **Bins** action.  
3.  Select the lines for the bins that you want to delete.  
4.  Choose the **Delete** action.  

If you choose the **Yes** button, the bin is deleted for use in the future, but the bin code in all warehouse entries remains the same.  

If you want to rename a bin so that all records associated with the bin are also renamed, including bin contents, warehouse activity lines, registered warehouse activity lines, warehouse worksheet lines, warehouse receipt lines, posted warehouse receipt lines, warehouse shipment lines, posted warehouse shipment lines, and warehouse entries, you can do so on the **Bins** page.  

## To rename a bin and change the bin code in all records  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  Select the location where you want to rename a bin or change the bin code, and then choose the **Bins** action.  
3.  Select the bin that you want to change and enter a new bin code in the **Code** field.  
4.  Choose the **Yes** button.  

> [!NOTE]  
>  If you choose **Yes** and there are many entries concerning this bin, for example, because you have not deleted warehouse documents for some time, it may take some time to rename all the records. Therefore, if you use this method, consider running the batch job **Delete Registered Whse. Documents** before you start the renaming process. Also note that the only documents that are deleted in this batch job are put-aways, picks, and movements.  
>   
>  If you are renaming a receiving bin or a shipping bin, all the posted receipts or shipments that refer to the bin in question are renamed.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
