---
title: "How to: Assign Exact Cost Reversing in Purchases"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exact cost reversing"
  - "return orders, assigning exact cost"
  - "purchase returns, assigning exact cost"
ms.assetid: 552030cb-f4c9-492d-b82d-d8d4d5106429
caps.latest.revision: 9
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Assign Exact Cost Reversing in Purchases
You may agree with your vendor to return a purchased item to them. When you have created a purchase return order and are ready to invoice it, you may want to revalue inventory using the unit cost that is connected to the original purchase entry. By default, a returned item is valued according to the current unit cost.  
  
 Two functions exist to assign the cost reversing automatically.  
  
|**Function**|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse**|Copies lines of one or more posted documents to be reversed.|  
|**Copy Document**|Copies both the header and lines of one posted or open document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected in the **Purchases & Payables Setup** window.|  
  
### To assign exact cost reversing manually  
  
1.  In the **Search** box, enter **Purchase Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Purchase Return Orders](../Purchasing/how-to-create-purchase-return-orders.md).  
  
3.  Choose the **Appl.\-to Item Entry** field, and then select the number of the original purchase entry number.  
  
 This links the purchase return order to the original purchase entry and ensures that the item is valued at the original unit cost.  
  
### To assign exact cost reversing automatically  
  
1.  In the **Search** box, enter **Purchase Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Purchase Return Orders](../Purchasing/how-to-create-purchase-return-orders.md).  
  
3.  On the **Home** tab, in the **Process**  group, choose **Get Posted Document Lines to Reverse**.  
  
4.  In the **Posted Purchase Document Lines** window, select the line or lines that you want to reverse, and then choose the **OK** button.  
  
 The selected line or lines are inserted under the purchase return order line. The **Appl.\-from Item Entry** field on the lines are filled with number of the reversed item ledger entry.  
  
> [!NOTE]  
>  If the line has item tracking, then the **Appl.\-to Item Entry** field is filled on the related line in the **Item Tracking Lines** window instead of on the purchase return line.  
  
## See Also  
 [How to: Reverse Posted Document Lines](../Finance/how-to-reverse-posted-document-lines.md)   
 [Design Details: Inventory Costing](../ApplicationDesign/design-details-inventory-costing.md)   
 [Posted Purchase Document Lines](../Topic/\($%20N_5855%20Posted%20Purchase%20Document%20Lines%20$\).md)   
 [Item Tracking Lines](../Topic/\($%20N_6510%20Item%20Tracking%20Lines%20$\).md)   
 [Appl.\-to Item Entry](../Topic/\($%20T_39_38%20Appl.-to%20Item%20Entry%20$\).md)   
 [Applies\-to Entry](../Topic/\($%20T_32_28%20Applies-to%20Entry%20$\).md)   
 [How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../Finance/how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)