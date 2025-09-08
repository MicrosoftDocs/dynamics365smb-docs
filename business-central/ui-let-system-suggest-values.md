---
title: Let Business Central suggest values
description: To avoid manual calculations and complete tasks quickly and accurately, you can set up automatic data entry so that Business Central fills in selected fields.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 39, 251, 981
ms.date: 04/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Let Business Central suggest values

[!INCLUDE[prod_short](includes/prod_short.md)] helps you complete tasks faster and more accurately by prefilling fields or completing lines with data that you would otherwise calculate and enter manually. Although such automatic data entry is always correct, you can change it afterwards if you want to.

This article contains a selection of such functionality. More sections will be added in future updates of [!INCLUDE[prod_short](includes/prod_short.md)].

## Autofill fields with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner-section.md)]

When you draft a new record or edit an existing record, Copilot suggests values for editable fields on the page. Learn more in [Autofill fields with Copilot](autofill-fields-with-copilot.md).

## The **Suggest Balancing Amount** check box on the **General Journal Batches** page

When, for example, you're entering general journal lines for multiple expenses that must all be posted to the same bank account, then each time you enter a new journal line for an expense, you can have the **Amount** field on the bank account line automatically updated to the amount that balances the expenses. For more information about working with general journals, see [Work with General Journals](ui-work-general-journals.md).

### To have the **Amount** field on balancing general journal lines filled automatically

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
1. On the line for your preferred general journal batch, choose the **Suggest Balancing Amount** check box.
1. Open the general journal and proceed to register and post transactions using the described functionality for automatic entry of a field value.       

For information about how to set up a personal general journal batch, for example, for expense handling, see [Work with General Journals](ui-work-general-journals.md).

## The **Automatically Fill Date Received** field on the **Payment Registration** page

The **Register Customer Payments** page shows outstanding incoming payments as lines that represent sales documents where an amount is due for payment. For more information about applying customer payments, see [Reconcile Customer Payments from a List of Unpaid Sales Documents](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md).

Your main actions on the page are to fill in the **Payment Made** check box and the **Date Received** field. You can set [!INCLUDE[prod_short](includes/prod_short.md)] up to automatically enter work date in the **Date Received** field when you select the **Payment Made** check box.

### To have the **Date Received** field on the **Payment Registration** page filled automatically

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Registration Setup**, and then choose the related link.
1. Select the **Automatically Fill Date Received** check box.
1. Open the **Register Customer Payments** page and proceed to process incoming customer payments using the described functionality for automatic entry of a field value.

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
