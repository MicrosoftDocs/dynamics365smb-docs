---
title: "How to: Assign Exact Cost Reversing in Sales"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales returns, exact cost reversing"
  - "returns, sales"
ms.assetid: 557605a5-2dbe-411e-be4c-d881907e6756
caps.latest.revision: 6
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
# How to: Assign Exact Cost Reversing in Sales
You may agree to compensate a customer by letting them return a sold item against a sales return order. When you invoice the sales return order, you want to revalue the item at the unit cost that is connected to the original sales entry by assigning the exact cost in the reversal. By default, a returned item is valued according to the current unit cost.  
  
 Two functions exist to assign the cost reversing automatically.  
  
|**Function**|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse**|Copies lines of one or more posted documents to be reversed.|  
|**Copy Document**|Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **\($ T\_311\_6602 Exact Cost Reversing Mandatory $\)** check box is selected in the **\($ N\_459 Sales & Receivables Setup $\)** window.|  
  
### To assign exact cost reversing manually  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md).  
  
3.  Choose the **Appl.\-from Item Entry** field, and then select the number of the original sales entry number.  
  
 This links the sales return order to the original sales entry and ensures that the item is valued at the original unit cost.  
  
### To assign exact cost reversing automatically  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md).  
  
3.  On the **Home** tab, in the **Process**  group, choose **Get Posted Document Lines to Reverse**.  
  
4.  In the **Posted Sales Document Lines** window, select the line or lines that you want to reverse, and then choose the **OK** button.  
  
 The selected line or lines are inserted under the sales return order line. The **Appl.\-from Item Entry** field on the lines are filled with number of the reversed item ledger entry.  
  
> [!NOTE]  
>  If the line has item tracking, then the **Appl.\-from Item Entry** field is filled on the related line in the **\($ N\_6510 Item Tracking Lines $\)** window instead of on the sales return line.  
  
## See Also  
 [How to: Reverse Posted Document Lines](../Finance/how-to-reverse-posted-document-lines.md)   
 [Design Details: Inventory Costing](../ApplicationDesign/design-details-inventory-costing.md)   
 [\($ N\_5850 Posted Sales Document Lines $\)](../Topic/\($%20N_5850%20Posted%20Sales%20Document%20Lines%20$\).md)   
 [\($ N\_6510 Item Tracking Lines $\)](../Topic/\($%20N_6510%20Item%20Tracking%20Lines%20$\).md)   
 [\($ T\_37\_5811 Appl.\-from Item Entry $\)](../Topic/\($%20T_37_5811%20Appl.-from%20Item%20Entry%20$\).md)   
 [\($ T\_32\_28 Applies\-to Entry $\)](../Topic/\($%20T_32_28%20Applies-to%20Entry%20$\).md)   
 [How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../Finance/how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)