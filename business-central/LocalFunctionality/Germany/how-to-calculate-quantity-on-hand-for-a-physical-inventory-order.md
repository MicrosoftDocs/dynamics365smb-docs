---
    title: How to Calculate Quantity On Hand for a Physical Inventory Order
    description: After you have created the physical inventory order and after you have entered the physical inventory order lines, you must have the program calculate the field Qty. Expected (Base) for every physical inventory order line.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Calculate Quantity On Hand for a Physical Inventory Order
After you have created the physical inventory order and after you have entered the physical inventory order lines, you must have the program calculate the field Qty. Expected (Base) for every physical inventory order line.  

If [!INCLUDE[d365fin](../../includes/d365fin_md.md)] created this physical inventory order lines automatically, you could decide in the request page for the batch job whether to calculate the expected quantity or not. If you have created the physical inventory order lines manually or if you changed them in the meantime, you have to calculate the expected quantities manually. You can calculate quantities in two ways as described in the following section.  

## To calculate the expected quantity on the physical inventory order  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Order**, and then choose the related link.  
2.  Open the physical inventory order that you want to calculate the expected quantity for.  
3.  To calculate the expected quantity of only one physical inventory order line, choose the **Calculate Qty. Expected** action, and then choose the **This Line** action.  
4.  To calculate the expected quantity in all physical inventory order lines, choose the **Calculate Qty. Expected** action, and then choose the **All Lines** action.  

    In the dialog that appears, choose to calculate the quantities for all lines or for those lines that have not yet been calculated.  

If [!INCLUDE[d365fin](../../includes/d365fin_md.md)] has already calculated the expected quantity, it shows this by placing a check mark in the **Qty. Exp. Calculated** field in the inventory order line.  

> [!NOTE]  
>  The process of taking the inventory and recording it in the physical inventory recording is independent from the calculation of the expected quantities.  

You must calculate the expected quantities for all physical inventory order lines of a physical inventory order before you can set the Status field to **Finished**. This is because [!INCLUDE[d365fin](../../includes/d365fin_md.md)] compares the expected and the recorded quantities and calculates the differences for posting.  

## See Also  
 [Enter Physical Inventory Orders](how-to-enter-physical-inventory-orders.md)   
 [Physical Inventory Recording - Counting Physical Inventory](physical-inventory-recording-counting-physical-inventory.md)   
 [Finish a Physical Inventory Order](how-to-finish-a-physical-inventory-order.md)   
 [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](physical-inventory-order-lines-with-item-tracking-lines.md)  
 [Count, Adjust, and Reclassify Inventory](../../inventory-how-count-adjust-reclassify.md)
