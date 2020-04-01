---
    title: How to Block Sales to Customers  Items from Sales or Purchasing
    description: In Business Central, an item can be marked as blocked for sales, blocked for purchase, or blocked for all purposes.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Block Customers
You can block a customer, for example because of insolvency, so that the customer cannot be added to sales documents or so that no transactions can be posted for the customer.

In addition to blocking a customer, you can set receivable transactions for the customer to be on hold in connection with reminders. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).   

The following table describes the different blocking options.  

|Option|Description|  
|--------------------|------------|  
|**Blank**|Transactions are allowed for this customer.|
|**Ship**|New orders and new shipments cannot be created for this customer. Existing shipments not yet invoiced can be invoiced.|  
|**Invoice**|New orders, new shipments, and new invoices cannot be created for this customer. Existing shipments not yet invoiced cannot be invoiced.|  
|**All**|No transaction is allowed for this customer, including payments.|  

## To block a customer  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Select a customer, and then choose the **Edit** action.
3. Fill in the **Blocked** field with one of the options described above.

## See Also  
[Register New Customers](sales-how-register-new-customers.md)  
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Managing Receivables](receivables-manage-receivables.md)  
