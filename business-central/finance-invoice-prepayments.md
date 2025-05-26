---
title: Invoice prepayments
description: Learn how to use prepayments to invoice and collect deposits from customers and remit deposits to vendors in Business Central. 
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.form: 42, 42, 48, 50, 52, 9305, 9307
ms.date: 07/19/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Invoicing prepayments

[!INCLUDE [prepayment_def](includes/prepayment_def.md)]

[!INCLUDE [prepayment_req](includes/prepayment_req.md)]

For example, you can specify a total amount for the entire order, or you can distribute the prepayment across each line on the order. You can also send additional prepayment invoices if, for example, additional items are added to the order. You can increase quantities or add new lines to an order after issuing a prepayment, and then you can post another prepayment invoice.  

> [!NOTE]
> If you want to delete a line for which a prepayment has already been invoiced, you must issue a prepayment credit memo before you can delete the line.

The following table describes a sequence of tasks, with links to the articles that describe them.

|**To**|**See**|  
|------------|-------------|  
|Set up prepayment posting groups and number series, and set up default prepayment percentages for customers, vendors, and items.|[Set Up Prepayments](finance-set-up-prepayments.md)|
|Create an order, adjust the prepayment amounts, and issue an invoice for prepayment amounts.|[Create Prepayment Invoices](finance-how-to-create-prepayment-invoices.md)|  
|Issue an additional prepayment invoice, either for additional items or for an additional deposit on the original order, or issue a prepayment credit memo.|[Correct Prepayments](finance-how-to-correct-prepayments.md)|  

## Related information

[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
