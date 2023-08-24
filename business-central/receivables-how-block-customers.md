---
    title: How to Block Sales to Customers
    description: If needed, you can block a customer from being included on sales documents and other sales transactions.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# Block Customers
You can block a customer, for example because of insolvency, so that the customer cannot be added to sales documents or so that no transactions can be posted for the customer.

In addition to blocking a customer, you can set receivable transactions for the customer to be on hold in connection with reminders. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).   

The following table describes the options for blocking customers.  

|Option|Description|  
|--------------------|------------|  
|**Blank**|Transactions are allowed for this customer.|
|**Ship**|New orders and new shipments cannot be created for this customer. Existing shipments not yet invoiced can be invoiced.|  
|**Invoice**|New orders, new shipments, and new invoices cannot be created for this customer. Existing shipments not yet invoiced cannot be invoiced. You can still send reminders and finance charge memos to the customer.|  
|**All**|No transaction is allowed for this customer, including payments.|  

## To block a customer  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Select a customer, and then choose the **Edit** action.
3. In the **Blocked** field, choose what to block, as described in the table above.

## See Also  
[Register New Customers](sales-how-register-new-customers.md)  
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Managing Receivables](receivables-manage-receivables.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]