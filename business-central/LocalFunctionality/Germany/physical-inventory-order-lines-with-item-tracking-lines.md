---
    title: Physical Inventory Order Lines With Item Tracking Lines
    description: Item tracking lines are used to enter serial numbers and lot numbers for physical inventory order lines.
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
# Physical Inventory Order Lines With Item Tracking Lines
Item tracking lines are used to enter serial numbers and lot numbers for physical inventory order lines.  

 The program will obey the item tracking lines only if there is a check mark in the field Use Tracking Lines of the physical inventory order line.  

 The program places the checkmark automatically depending on the settings for the item tracking code from the item table. You can also set or delete the check mark in the check box manually. Placing a check mark here is only possible, if the item of the current physical inventory order line has been posted all the time using serial nos. or lot nos.  

 If there is a check mark in this check box the program uses 3 places, where tracking information can be found:  

-   expected item tracking lines  

-   physical counts with serial nos. and lot nos. on the physical inventory recording line.  

-   item tracking lines to post.  

 **Expected Tracking Lines:**  

 If you have the program to calculate the field Qty. Expected (Base) on the physical inventory order line, the program also calculates a list for the current item containing quantities with serial nos. and lot nos. which should be available on stock.  

 The program includes in the calculation all item ledger entries, which have been posted until the Posting Date of the inventory order header and which have the same values on the 4 fields Item No., Variant Code, Location Code and Bin Code on the physical inventory order line.  

 You can view the expected tracking lines for the current physical inventory order line. Choose **Line**, **Item Tracking Lines**, **Expected Tracking Lines**. The window Expect. Phys. Inv. Track. List opens.  

 **Serial No./Lot No. On The Physical Inventory Recording Line:**  

 If you enter the recorded quantities on the physical inventory recording, you can enter serial nos./lot nos. to. When finishing the physical inventory recording, the program will assign the physical inventory recording lines with serial nos./ lot nos. to physical inventory order lines.  

 You can view the counted serial nos. and lot nos. for the current physical inventory order line. Choose **Line**, **Recording Lines**. The window Phys. Invt. Recording Lines opens.  

 **Item Tracking Lines To Post:**  

 When finishing the physical inventory order, the program compares the expected quantity and the recorded (counted) quantity and calculates the difference. If you have the program also to obey item tracking lines (by placing a check mark on the field Use Tracking Lines of the physical inventory order line), the program also calculates the differences between the expected serial nos. and lot nos. and the recorded serial nos. and lot nos. The list of the calculated differences will be used by the program when posting the physical inventory order.  

 You can view the item tracking lines to post for the current physical inventory order line. Choose **Line**, **Item Tracking Lines**, **All Diff. Tracking Lines**. The window **Phys. Invt. Item Track. List** opens.  

 For more information, see [Example - Inventory Order Line with Tracking Lines](example-inventory-order-line-with-tracking-lines.md).  

 You can have the program to print the item tracking lines optional when printing the report Phys. Invt. Order Diff. List for the inventory order lines.  

## See Also  
 [Enter Physical Inventory Orders](how-to-enter-physical-inventory-orders.md)   
 [Calculate Quantity On Hand for a Physical Inventory Order](how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [Physical Inventory Recording - Counting Physical Inventory](physical-inventory-recording-counting-physical-inventory.md)   
 [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md)   
 [Finish a Physical Inventory Order](how-to-finish-a-physical-inventory-order.md)   
 [Analyze Physical Inventory Differences](how-to-analyze-physical-inventory-differences.md)
