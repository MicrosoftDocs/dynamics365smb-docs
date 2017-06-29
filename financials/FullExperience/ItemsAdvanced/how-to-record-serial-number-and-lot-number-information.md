---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Record Serial Number and Lot Number Information
If you need to link special information to a specific item tracking number, for example, for quality assurance, you can do so in a serial or lot number information card.  
  
### To record serial or lot number information  
  
1.  In the **Search** box, enter **Sales Orders**, and then select the related link.  
  
2.  Create a sales order line for an item-tracked item.  
  
     Proceed to assign serial and lot numbers to the sales order line.  
  
3.  On the **Lines** FastTab, choose **Line**, and then choose **Item Tracking Lines**.  
  
4.  In the **Serial No.** field, enter **SN1**, in the **Lot No.** field, enter **LOT1**, and then enter **1** in the **Quantity \(Base\)** field.  
  
5.  On the **Navigate** tab, in the **Line** group, choose, for example, **Serial No. Information Card**.  
  
     The **Serial No.** and **Lot No.** fields are prefilled from the item tracking line.  
  
6.  Enter a short piece of information in the **Description** field, for example about the condition of the item.  
  
7.  On the **Navigate** tab, in the **Serial No.** group, choose **Comment** to create a separate comment record.  
  
8.  Select the **Blocked** check box to exclude the serial or lot number from any transactions.  
  
### To modify existing serial\/lot number information  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  From the **Item Card** window, on the **Navigate** tab, in the **History** group, choose the **Entries** button, and then choose **Ledger Entries**.  
  
3.  Choose the **Lot No.** or **Serial No.** field. If information exists for the item tracking number, then the **Lot No. Information List** or **Serial No. Information List** window opens.  
  
4.  Select a card, and then, on the **Actions** tab, in the **Functions** group, choose **Lot No.\/Serial No. Information Card**.  
  
5.  Modify the short description text, the comment record, or the **Blocked** field.  
  
 You cannot modify the serial or lot numbers or quantities. To do so, you must reclassify the item ledger entry in question. For more information, see [Reclassifying Lot or Serial Numbers](../FullExperience/how-to-reclassify-lot-numbers-and-serial-numbers.md).  
  
## See Also  
 Item Tracking Lines   
 Serial No. Information Card