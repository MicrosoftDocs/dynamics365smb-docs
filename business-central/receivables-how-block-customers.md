---
    title: How to Block Sales to Customers  Items from Sales or Purchasing
    description: In Business Central, an item can be marked as blocked for sales, blocked for purchase, or blocked for all purposes.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/17/2018
    ms.author: sgroespe

---
# Block Customers
You can block a customer, for example because of insolvency, so that the customer cannot be added to sales documents or so that no transactions can be posted for the customer.  

The following table describes the different blocking options.  

|Option|Description|  
|--------------------|------------|  
|**Blankd**|Transactions are allowed for this customer.|
|**Ship**|New orders and new shipments cannot be created for this customer. Existing shipments not yet invoiced can be invoiced.|  
|**Invoice**|New orders, new shipments, and new invoices cannot be created for this customer. Existing shipments not yet invoiced cannot be invoiced.|  
|**All**|No transaction is allowed for this customer, including payments.|  

## To block a customer  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.
2. Select a customer, and then choose the **Edit** action.
3. Fill in the **Blocked** field with one of the options described above.

## See Also  
[Register New Customers](sales-how-register-new-customers.md)  
[Managing Receivables](receivables-manage-receivables.md)  
