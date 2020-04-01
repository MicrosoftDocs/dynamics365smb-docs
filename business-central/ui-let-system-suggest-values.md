---
title: Setting Up Suggested Field Values | Microsoft Docs
description: To avoid manual calculations and complete tasks quickly and accurately, you can set up automatic data entry so that Business Central fills in selected fields.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: sgroespe

---
# Letting [!INCLUDE[d365fin](includes/d365fin_md.md)] Suggest Values
[!INCLUDE[d365fin](includes/d365fin_md.md)] can help you complete tasks quicker and more correctly by prefilling fields or complete lines with data that you would otherwise have to calculate and enter yourself. Although such automatic data entry is always correct, you can change it afterwards if you want to.

Functionality that enters field values for you is typically offered for tasks where you enter large volumes of transactional data and want to avoid errors and save time. This topic contains a selection of such functionality. More sections will be added in future updates of [!INCLUDE[d365fin](includes/d365fin_md.md)].

## The **Suggest Balancing Amount** check box on the **General Journal Batches** page
When, for example, you are entering general journal lines for multiple expenses that must all be posted to the same bank account, then each time you enter a new journal line for an expense, you can have the **Amount** field on the bank account line automatically updated to the amount that balances the expenses. For more information about working with general journals, see [Working with General Journals](ui-work-general-journals.md).

### To have the **Amount** field on balancing general journal lines filled automatically
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.
2. On the line for your preferred general journal batch, choose the **Suggest Balancing Amount** check box.
3. Open the general journal and proceed to register and post transactions using the described functionality for automatic entry of a field value.       

For information about how to set up a personal general journal batch, for example, for expense handling, see [Working with General Journals](ui-work-general-journals.md).

## The **Automatically Fill Date Received** field on the **Payment Registration** page
The **Payment Registration** page shows outstanding incoming payments as lines that represent sales documents where an amount is due for payment. For more information about applying customer payments, see [Reconcile Customer Payments from a List of Unpaid Sales Documents](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md).

You main actions on the page are to fill in the **Payment Made** check box and the **Date Received** field. You can set [!INCLUDE[d365fin](includes/d365fin_md.md)] up to automatically enter work date in the **Date Received** field when you select the **Payment Made** check box.

### To have the **Date Received** field on the **Payment Registration** page filled automatically
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Registration Setup**, and then choose the related link.
2. Select the **Automatically Fill Date Received** check box.
3. Open the **Payment Registration** page and proceed to process incoming customer payments using the described functionality for automatic entry of a field value.

## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Finance](finance.md)
