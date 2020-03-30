---
    title: How to Plan Put-aways in Worksheets | Microsoft Docs
    description: If your location requires both put-away and receive processing, and you want to plan put-away instructions for a number of receipts, rather than have employees follow the instructions that application creates for separate posted receipts, you can use the put-away worksheet.
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
# Plan Put-aways in Worksheets
If your location requires both put-away and receive processing, and you want to plan put-away instructions for a number of receipts, rather than have employees follow the instructions that application creates for separate posted receipts, you can use the put-away worksheet.  

To set up your warehouse so that receipt lines are available to you in the put-away worksheet as soon as they are posted, select the **Use Put-away Worksheet** field on the **Warehouse** FastTab of the location card. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

If you do not select this field, application will automatically create put-away instructions for receipts as they are posted.  

> [!NOTE]  
>  Regardless of the status of the **Use Put-away Worksheet** field on the location card, you can always get put-away instruction lines, that is, posted receipt lines, into the put-away worksheet by doing the following:  
>   
>  1.  On the **Warehouse Put-away** page, press Ctrl+D to delete the entire put-away instruction, or select the lines that you want to process in the worksheet and delete them.  
> 2.  Continue the process in as many put-aways as you wish, until you have deleted the lines you want to work on in the worksheet. Now choose **Put-away Worksheets** and proceed with planning.  

## To plan instructions in the put-away worksheet  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Put-away Worksheet**, and then choose the related link.  
2.  Choose the **Get Warehouse Documents** action. The **Put-away Selection** page opens.  

    You see all the posted receipts and registered internal put-aways that have been forwarded to the put-away function, including those for which put-away instructions have already been created. Documents with put-away lines that have been completely put away and registered are not shown on this list.  

3. Select the documents that you want to work on in the worksheet. You can work on lines from several documents at the same time.  

    > [!NOTE]  
    >  If you try to select a receipt or internal put-away document for which you have already created instructions for all its lines, application informs you that there is nothing to handle.  

4. Fill in the **Sorting Method** field to sort the lines the way you prefer.  

    > [!NOTE]  
    >  The way the lines are sorted in the worksheet does not carry through automatically to the put-away instruction, but the same sorting possibilities exist, along with bin ranking. The line order you plan in the worksheet is thus easily recreated when you create the put-away instructions or by sorting in the put-away instructions.  

5.  Fill in the **Qty. to Handle** field. Choose the **Autofill Qty.to Handle** action, or fill in the fields manually.  
6.  If necessary, edit the lines manually. You can delete lines, for example, if some items need to be put away in a bin far away from the bins for the other items.  

    > [!NOTE]  
    >  Lines deleted are only deleted from this worksheet, not from the put-away selection list.  

7.  Choose the **Create Put-away** action. The **Create Document** page opens, where you can add more information to the put-away you are creating, as follows:  

    -   You can assign the put-away to a specific employee.  
    -   You can sort the put-away instruction lines as you did in the worksheet or by bin ranking. When you sort according to bin ranking, the Take lines appear first, since most receipt bins have a 0 bin ranking, and the Place lines appear last, starting with the bins with the lowest bin ranking. If you have structured your warehouse so bins of similar bin ranking are side by side, sorting lines in this way will ultimately save steps for your warehouse employees.  
    -   You can choose not to see the intermediate lines created when application breaks a larger unit of measure to smaller units of measure by selecting the **Set Breakbulk Filter** field. For more information, see [Enable Automatic Breaking Bulk with Directed Put-away and Pick](warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md).  
    -   You can choose not to have the **Qty. to Handle** field automatically filled in on the put-away instructions.  
    -   You can choose to print the document immediately.  

8.  Choose the **OK** button, and application creates the put-away according to your requests.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
