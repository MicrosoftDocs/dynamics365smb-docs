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
# How to: View Unposted and Posted Blanket Sales Order Lines
The link between the blanket sales order and the originating sales order, and any other sales document, is retained after posting as a list of posted and unposted sales order invoice lines.  
  
### To view unposted entries  
  
1.  Select the line in question and then on the **Lines** FastTab, click **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), **Line**, **Unposted Lines**. The following options are available:  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Orders**|Specifies open orders associated with the selected line.|  
    |**Invoices**|Specifies open invoices that have been associated with the selected line. Open invoices are manually associated with a blanket order by entering the blanket order number on the sales invoice line.|  
    |**Return Orders:**|Specifies open return orders that have been associated with the selected line.|  
    |**Credit Memos**|Specifies open credit memos that have been associated with the selected line.|  
  
2.  In the **Sales Lines** window, select the appropriate document. On the **Lines** FastTab, click **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), **Line**, **Show Document** to view the entry.  
  
### To view posted entries  
  
1.  Select the line in question and then on the **Lines** FastTab, click **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), **Line**, **Posted Lines**. The following options are available:  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Shipments**|Posted shipments associated with the selected line.|  
    |**Invoices**|Posted invoices associated with the selected line.|  
    |**Return Receipts**|Posted return receipts that have been associated with the selected line.|  
    |**Credit Memos**|Posted credit memos that have been associated with the selected line.|  
  
## See Also  
 [About Blanket Sales Orders](../Sales/about-blanket-sales-orders.md)   
 [How to: Create Blanket Sales Orders](../Sales/how-to-create-blanket-sales-orders.md)   
 [How to: View the Status of Blanket Sales Orders](../Sales/how-to-view-the-status-of-blanket-sales-orders.md)