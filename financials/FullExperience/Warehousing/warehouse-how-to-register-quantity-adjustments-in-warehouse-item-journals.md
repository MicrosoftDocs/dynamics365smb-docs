---
    title: How to Register Quantity Adjustments in Warehouse Item Journals | Microsoft Docs
    description: If your location uses directed put-away and pick, use the **Whse. Item Journal** to post, outside the context of the physical inventory, all positive and negative adjustments in item quantity that you know are real gains, such as items previously posted as missing that show up unexpectedly, or real losses, such as breakage.
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
# How to: Register Quantity Adjustments in Warehouse Item Journals
If your location uses directed put-away and pick, use the **Whse. Item Journal** to post, outside the context of the physical inventory, all positive and negative adjustments in item quantity that you know are real gains, such as items previously posted as missing that show up unexpectedly, or real losses, such as breakage.  
  
 Unlike posting adjustments in the inventory item journal, using the warehouse item journal gives you an additional level of adjustment that makes your quantity records even more precise at all times. The warehouse thus always has a complete record of how many items are on hand and where they are stored, but each adjustment registration is not posted immediately to the item ledger. In the registering process, credits or debits are made to the real bin with the quantity adjustment and a counterbalancing entry is made in an adjustment bin, a virtual bin with no real items. This bin is defined during in the **Invt. Adjustment Bin Code** on the location card. At regular intervals, you synchronize warehouse entries with the item ledger. For more information, [How to: Post Quantity Adjustments for Bins](../how-to-post-quantity-adjustments-for-bins.md).  
  
> [!NOTE]  
>  If the location does not use directed put-away and pick, simply use the **Item Journal** to post, outside the context of the physical inventory, all positive and negative adjustments in item quantity that you know are real gains or real losses. In that case, no adjustment with warehouse entries is required.  
  
### To register a discrepancy in item quantity  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Whse. Item Journal**, and then choose the related link.  
  
2.  Fill in the header information.  
  
3.  Fill in the **Item No.** field on the line.  
  
4.  Enter the bin in which you are putting the extra items or where you have found items to be missing.  
  
5.  Fill in the quantity that you observe as a discrepancy in the **Quantity** field. If you have found extra items, enter a positive quantity. If items are missing, enter a negative quantity.  
  
6.  On the **Actions** tab, in the **Registering** group, choose **Register.**  
  
#### Example  
 You find a few units of an item on a fork lift truck. You do not know where the units should be stored, but you can place them in a bin and register the quantity to this bin in the **Warehouse Item Journal** window. When you do this, a positive quantity is registered to the bin in which you have placed the items, and a negative quantity is registered in the adjustment bin.  
  
 The items found on the truck have most likely been registered to another bin, and at some point, a warehouse employee will observe and register a negative difference in quantity for this bin. Perhaps a pick has been suggested that cannot be fulfilled because items are missing from the bin, or a physical inventory has been performed for the item.  
  
 When the negative adjustment quantity is registered in the **Warehouse Item Journal** window, or a value in the **Qty. (Phys. Inventory)** field has been registered in the **Whse. Phys. Invt. Journal** window, a positive counterbalancing entry is made in the adjustment bin.  
  
## See Also  
 Whse. Phys. Invt. Journal   
 Warehouse Item Journal   
 Qty. (Phys. Inventory)%20$).md)   
 [Warehouse Adjustment Bin](../warehouse-adjustment-bin.md)   
 Warehouse Adjustment Bin   
 [How to: Post Quantity Adjustments for Bins](../how-to-post-quantity-adjustments-for-bins.md)