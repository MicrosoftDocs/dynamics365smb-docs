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
# Invoice Prepayments
Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You might require a deposit before you manufacture items to order, or you might require payment before you ship items to a customer. The prepayments functionality enables you to invoice and collect deposits required from customers or to remit deposits to vendors. Thus, you can ensure that all payments are posted against an invoice.  
  
 Prepayment requirements can be defined for a customer or vendor for all items or selected items. After you complete the required setup, you can generate prepayment invoices from sales and purchase orders for the calculated prepayment amount. You can change the amounts on the invoice as needed. For example, you can specify a total amount for the entire order. You can also send additional prepayment invoices if, for example, additional items are added to the order. You can increase quantities or add new lines to an order after issuing a prepayment, and then you can post another prepayment invoice. If you want to delete a line for which a prepayment has already been invoiced, you must issue a prepayment credit memo before you can delete the line.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Create an order, adjust the prepayment amounts, and issue an invoice for prepayment amounts.|[How to: Create Prepayment Invoices](../Finance/how-to-create-prepayment-invoices.md)|  
|Issue an additional prepayment invoice, either for additional items or for an additional deposit on the original order, or issue a prepayment credit memo.|[How to: Correct Prepayments](../Finance/how-to-correct-prepayments.md)|  
  
## See Also  
 [Set Up Prepayments](../Finance/set-up-prepayments.md)   
 [Walkthrough: Setting Up and Invoicing Sales Prepayments](../GettingStarted/walkthrough-setting-up-and-invoicing-sales-prepayments.md)