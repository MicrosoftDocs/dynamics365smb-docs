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
# How to: Assign Exact Cost Reversing in Sales
You may agree to compensate a customer by letting them return a sold item against a sales return order. When you invoice the sales return order, you want to revalue the item at the unit cost that is connected to the original sales entry by assigning the exact cost in the reversal. By default, a returned item is valued according to the current unit cost.  
  
 Two functions exist to assign the cost reversing automatically.  
  
|**Function**|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse**|Copies lines of one or more posted documents to be reversed.|  
|**Copy Document**|Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected in the **\($ N\_459 Sales & Receivables Setup $\)** window.|  
  
### To assign exact cost reversing manually  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md).  
  
3.  Choose the **Appl.-from Item Entry** field, and then select the number of the original sales entry number.  
  
 This links the sales return order to the original sales entry and ensures that the item is valued at the original unit cost.  
  
### To assign exact cost reversing automatically  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Enter a line for a returned item. For more information, see [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md).  
  
3.  On the **Home** tab, in the **Process**  group, choose **Get Posted Document Lines to Reverse**.  
  
4.  In the **Posted Sales Document Lines** window, select the line or lines that you want to reverse, and then choose the **OK** button.  
  
 The selected line or lines are inserted under the sales return order line. The **Appl.-from Item Entry** field on the lines are filled with number of the reversed item ledger entry.  
  
> [!NOTE]  
>  If the line has item tracking, then the **Appl.-from Item Entry** field is filled on the related line in the **Item Tracking Lines** window instead of on the sales return line.  
  
## See Also  
 [How to: Reverse Posted Document Lines](../Finance/how-to-reverse-posted-document-lines.md)   
 [Design Details: Inventory Costing](../ApplicationDesign/design-details-inventory-costing.md)   
 Posted Sales Document Lines   
 Item Tracking Lines   
 Appl.-from Item Entry   
 Applies-to Entry   
 [How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../Finance/how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)