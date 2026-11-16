---
title: Set up cash customers
description: This topic describes the steps required to set up the invoice with a customer number for customers who pay in cash.
author: brentholtorf
ms.topic: how-to
ms.search.form: 21, 22
ms.date: 06/16/2026
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Set up cash customers

To create an invoice, the customer must have a customer number. This is also true for cash sales where you don't have a customer account.  

## To set up a cash customer

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customer**, and then choose the related link.  
2. Choose **New** to open a new **Customer Card** page. 
3. In the **No.** field, enter **Cash**, for example.  
4. In the **Name** field, enter **Cash Sale**, for example.  
5. On the **Invoicing** FastTab, fill in the **Customer Posting Group** and the **Gen. Bus. Posting Group** fields.  

 Now you have set up a customer with enough information to create an invoice for a sale. Learn more about creating new customers in [Register New Customers](sales-how-register-new-customers.md).

> [!NOTE]  
> You might have chosen a posting group that is also used for domestic credit sales. If you want to maintain separate data on cash sales, for example, with a special sales or receivables account, you can set up an extra posting group for that purpose.  
>
> You must enter a number for a receivables account for the posting group, even though the balance in this account will always be 0 after you post an invoice.  

## Related information

[Managing Receivables](receivables-manage-receivables.md)  
[Register New Customers](sales-how-register-new-customers.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
