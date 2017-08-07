---
    title: How to Handle Serial Numbers and Lot Numbers on Transfer Orders | Microsoft Docs
    description: Procedures for handling serial and lot numbers that are being transferred between different locations are similar to those applied when items are sold and purchased.
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
# How to: Handle Serial Numbers and Lot Numbers on Transfer Orders
Procedures for handling serial and lot numbers that are being transferred between different locations are similar to those applied when items are sold and purchased.  
  
 However, the transfer order is unique in that shipment and receipt are both done from the same transfer line and, therefore, use the same instance of the **Item Tracking Lines** window. This means that item tracking numbers shipped from one location must be received unchanged at the other location.  
  
 The exact rules for handling item tracking numbers across your company are governed by the setup of the  **Item Tracking Code** table.  
  
### To handle serial/lot numbers on transfer orders  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer Orders**, and then choose the related link.  
  
2.  Open the transfer order you want to process. On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Tracking Lines**, and then choose **Shipment**.  
  
3.  In the **Item Tracking Lines** window, assign or select serial or lot numbers as for any other outbound item transaction.  
  
     When handling serial and lot numbers for transfer items, the items typically have numbers already assigned to them. Therefore, the process typically consists of selecting from existing serial or lot numbers.  
  
4.  Post the transfer order, first ship and then receive, to record that the items are transferred carrying their item tracking entries.  
  
 During the transfer, the **Item Tracking Lines** window remains locked for writing.  
  
## See Also  
 [How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 [How to: Select from Existing Serial Numbers and Lot Numbers](../how-to-select-from-existing-serial-numbers-and-lot-numbers.md)