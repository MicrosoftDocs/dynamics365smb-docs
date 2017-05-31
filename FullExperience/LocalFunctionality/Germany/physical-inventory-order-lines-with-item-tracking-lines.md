---
title: "Physical Inventory Order Lines With Item Tracking Lines"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, item tracking"
  - "inventory, physical orders"
ms.assetid: 0daee4d5-2c64-4d69-81f4-e8e916adf5a7
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# Physical Inventory Order Lines With Item Tracking Lines
Item tracking lines are used to enter serial nos. and lot nos. for physical inventory order lines.  
  
 The program will obey the item tracking lines only if there is a check mark in the field [\($ T\_5005351\_53 Use Tracking Lines $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_53-use-tracking-lines-$-.md) of the physical inventory order line.  
  
 The program places the checkmark automatically depending on the settings for the item tracking code from the item table. You can also set or delete the check mark in the check box manually. Placing a check mark here is only possible, if the item of the current physical inventory order line has been posted all the time using serial nos. or lot nos.  
  
 If there is a check mark in this check box the program uses 3 places, where tracking information can be found:  
  
-   expected item tracking lines  
  
-   physical counts with serial nos. and lot nos. on the physical inventory recording line.  
  
-   item tracking lines to post.  
  
 **Expected Tracking Lines:**  
  
 If you have the program to calculate the field [\($ T\_5005351\_50 Qty. Expected \(Base\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_50-qty.-expected-base-$-.md) on the physical inventory order line, the program also calculates a list for the current item containing quantities with serial nos. and lot nos. which should be available on stock.  
  
 The program includes in the calculation all item ledger entries, which have been posted until the [\($ T\_5005350\_21 Posting Date $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005350_21-posting-date-$-.md) of the inventory order header and which have the same values on the 4 fields [\($ T\_5005351\_20 Item No. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_20-item-no.-$-.md), [\($ T\_5005351\_21 Variant Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_21-variant-code-$-.md), [\($ T\_5005351\_22 Location Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_22-location-code-$-.md) and [\($ T\_5005351\_23 Bin Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_23-bin-code-$-.md) on the physical inventory order line.  
  
 You can view the expected tracking lines for the current physical inventory order line. Click **Line**, **Item Tracking Lines**, **Expected Tracking Lines**. The window Expect. Phys. Inv. Track. List opens.  
  
 **Serial No.\/Lot No. On The Physical Inventory Recording Line:**  
  
 If you enter the recorded quantities on the physical inventory recording, you can enter serial nos.\/lot nos. to. When finishing the physical inventory recording, the program will assign the physical inventory recording lines with serial nos.\/ lot nos. to physical inventory order lines.  
  
 You can view the counted serial nos. and lot nos. for the current physical inventory order line. Click **Line**, **Recording Lines**. The window Phys. Invt. Recording Lines opens.  
  
 **Item Tracking Lines To Post:**  
  
 When finishing the physical inventory order, the program compares the expected quantity and the recorded \(counted\) quantity and calculates the difference. If you have the program also to obey item tracking lines \(by placing a check mark on the field [\($ T\_5005351\_53 Use Tracking Lines $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_53-use-tracking-lines-$-.md) of the physical inventory order line\), the program also calculates the differences between the expected serial nos. and lot nos. and the recorded serial nos. and lot nos. The list of the calculated differences will be used by the program when posting the physical inventory order.  
  
 You can view the item tracking lines to post for the current physical inventory order line. Click **Line**, **Item Tracking Lines**, **All Diff. Tracking Lines**. The window **\($ N\_5005368 Phys. Invt. Item Track. List $\)** opens.  
  
 For more information, see [Example \- Inventory Order Line with Tracking Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/example-inventory-order-line-with-tracking-lines.md).  
  
 You can have the program to print the item tracking lines optional when printing the report [\($ R\_5005350 Phys. Invt. Order Diff. List $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-r_5005350-phys.-invt.-order-diff.-list-$-.md) for the inventory order lines.  
  
## See Also  
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)   
 [How to: Calculate Quantity On Hand for a Physical Inventory Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [Physical Inventory Recording \- Counting Physical Inventory](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-recording-counting-physical-inventory.md)   
 [How to: Finish a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-recording.md)   
 [How to: Finish a Physical Inventory Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-order.md)   
 [How to: Analyze Physical Inventory Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-analyze-physical-inventory-differences.md)