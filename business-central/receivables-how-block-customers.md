---
title: How to block sales to customers
description: If needed, you can block a customer from being included on sales documents and other sales transactions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 07/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Block customers
You can block a customer, for example because of insolvency, so that the customer can't be added to sales documents or so that no transactions can be posted for the customer.

In addition to blocking a customer, you can set receivable transactions for the customer to be on hold in connection with reminders. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).   

The following table describes the options for blocking customers.  

|Option|Description|  
|--------------------|------------|  
|**Blank**|Transactions are allowed for this customer.|
|**Ship**|New orders and new shipments can't be created for this customer. Existing shipments not yet invoiced can be invoiced.|  
|**Invoice**|New orders, new shipments, and new invoices can't be created for this customer. Existing shipments not yet invoiced can't be invoiced. You can still send reminders and finance charge memos to the customer.|  
|**All**|No transaction is allowed for this customer, including payments.|  

## To block a customer  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.
2. Select a customer, and then choose the **Edit** action.
3. In the **Blocked** field, choose what to block, as described in the table above.

## Related information  
[Register New Customers](sales-how-register-new-customers.md)  
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Managing Receivables](receivables-manage-receivables.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
