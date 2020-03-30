---
title: Post Intercompany Documents and Journals| Microsoft Docs
description: Use intercompany documents to post transactions with your intercompany partners.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 04/01/2020
ms.author: sgroespe

---
# Work with Intercompany Documents and Journals
You use intercompany documents or journals to post transactions with your intercompany partners. When you post an intercompany document or journal line in your company, a corresponding document or journal line is created in your intercompany outbox that you can transfer to your partner. Your partner can then post the corresponding transaction in their company, without having to re-enter the data.

For sales and purchase documents, the intercompany partner code on the involved customer or vendor ensures that all orders and invoices generated pertaining to transactions with these companies will produce corresponding documents in the partner company, resulting in correct balancing of the accounts.

For intercompany general journal lines, you do not need to specify the accounts for an individual set of books, but simply give the identification of the partner company. Corresponding intercompany general journal lines are then created in the partner company that result in the balancing of the books of both companies involved in a transaction.

## To fill in and send an intercompany sales order
You can send sales and purchase orders and return orders before posting. Invoices and credit memos cannot be sent until they are posted.

The following procedure describes how to fill in and send an intercompany sales order. The same steps apply to intercompany purchase orders and return orders, and to posted intercompany invoices and credit memos.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Choose **New** to create a new sales order. For more information, see [Sell Products](sales-how-sell-products.md).  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Make sure the customer is an intercompany partner.
5. To send the sales order before you post it, choose the **Send IC Sales Order** action.

> [!NOTE]
> If you do perform step 4, then the sales order will be moved to your intercompany outbox where you can send it later. For more information, see [Manage the Intercompany Inbox and Outbox](intercompany-how-manage-intercompany-inbox.md).

## To fill in and post an intercompany journal
When you post an intercompany general journal line in your company, a corresponding journal line is created in your intercompany outbox that you can transfer to your partner. Your partner can then post the corresponding transaction in their company, without having to re-enter the data.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany General Journals**, and then choose the related link.  
2. Open the relevant journal batch. For more information, see [Working with General Journals](ui-work-general-journals.md).
3. Fill in the fields as necessary.
4. In the **IC Partner G/L Acc. No.** field, enter the intercompany general ledger account that the amount will be posted to in your partner's company.

    > [!NOTE]
    > This field must be filled in on a line with a bank account or general ledger account in either the **Account No.** field or the **Bal. Account No.** field.  
5. Choose the **Post** action.

The involved entries are posted in your company and a journal with the corresponding entries are created in your intercompany outbox that you can send to your partner company. For more information, see [Manage the Intercompany Inbox and Outbox](intercompany-how-manage-intercompany-inbox.md).

## See Also
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
