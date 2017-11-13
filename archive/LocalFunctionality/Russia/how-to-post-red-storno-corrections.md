---
    title: How to Post Red Storno Corrections
    description: You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*.

    documentationcenter: ''
    author: SorenGP

    ms.prod: "dynamics-nav-2017"
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Post Red Storno Corrections
You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*. You can use red storno posting to post the following inventory entries:  

- Corrective entries in the item journal.  
- Reversal of item documents such as item receipts and item shipments.  
- Posting item revaluation or item reclassification journals.  
- Periodic adjustments of item costs.  

> [!NOTE]  
>  You must enable red storno in the **Inventory Setup** window before you can post corrective entries. For more information, see [Inventory Setup](inventory-setup.md).  

## To post corrective entries in the item journal  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Journal**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Entry Type**|Select the same entry type as the original posting.|  
    |**Quantity**|Enter the quantity with the opposite sign of the original posting, such as **-4**.|  
    |**Red Storno**|Select to post as a corrective posting.|  

     You must also select the appropriate entries in the **Applies-to Entry** or **Applies-from Entry** fields.  

3.  Post the journal.  

The correction is posted, and any general ledger account correspondence that you have set up will be considered.  

## To reverse item documents  

1.  To reverse an item receipt, Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Receipt**, and then choose the related link.  

    To reverse an item shipment, Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Shipment**, and then choose the related link.  

2.  On the **General** FastTab, select the **Correction** check box.  
3.  Choose the **Copy Document** action.  
4.  In the **Copy Document** window, set the appropriate filters, and then choose the **OK** button.  
5.  Make the needed changes to quantity and amounts.  

    You must also select the appropriate entries in the **Applies-to Entry** or **Applies-from Entry** fields. These fields identify the incorrectly posted document.  

6.  Post the document.  

## To post item revaluation or item reclassification journals  

1.  To post an item revaluation, Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Revaluation Journal**, and then choose the related link.  

    To post an item reclassification, Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Reclass Journal**, and then choose the related link.  

2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Applies-to Entry**|Specifies the item entry that you want to revalue or reclassify.|  
    |**Applies-from Entry**|Specifies the item entry that you want to revalue or reclassify.|  
    |**Red Storno**|Select to post as a corrective posting.|  

3.  Post the document.  

## See Also  
[Setting Up Inventory](../../inventory-setup-inventory.md)   
