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
# Set Up Prepayments
Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You might require a deposit before you manufacture items to order, or you might require payment before you ship items to a customer. The prepayments functionality enables you to invoice and collect deposits required from customers or to remit deposits to vendors. Thus, you can ensure that all payments are posted against an invoice.  
  
 Before you can post prepayment invoices, you have to set up the posting accounts in the general ledger, and you have to set up number series for prepayment documents.  
  
 You can define the percentage of the line amount that will be invoiced for prepayment, for a customer or vendor, for all items or selected items. After you complete the setup, you can generate prepayment invoices from sales and purchase orders. You can use the default percentages for each sales or purchase line, or you can change the amounts on the invoice as needed. For example, you can specify a total amount for the entire order.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Set up the general ledger accounts in which prepayments will be stored until the items are shipped.|"Set Up G\/L Accounts for Prepayments" in [Setting Up Prepayments](../how-to-define-prepayment-percentages.md)|  
|Assign the general ledger accounts for prepayments in the general posting setup.|"Add Prepayment Accounts to the General Posting Setup" in [Setting Up Prepayments](../how-to-define-prepayment-percentages.md)|  
|Set up number series for prepayment documents.|"Set Up Number Series for Prepayment Documents to the General Posting Setup" in [Setting Up Prepayments](../how-to-define-prepayment-percentages.md)|  
|Set up default prepayment percentages that apply to all items for one customer, or to one item for a specific customer, customer group, or all customers.|"Set Up Prepayment Percentages for Items, Customers, and\/or Vendors" in [Setting Up Prepayments](../how-to-define-prepayment-percentages.md)|  
  
## See Also  
 [Invoice Prepayments](../invoice-prepayments.md)